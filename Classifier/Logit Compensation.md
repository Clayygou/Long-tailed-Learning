

对于长尾学习任务，由于数据的不平衡，最后一层的输出logit通常存在偏差。Logit补偿的目的是消除数据不平衡造成的偏差，学习对边界的校正.



    import math
    import torch
    import torch.nn as nn
    import torch.nn.functional as F
    import numpy as np
    
    
    class LogitAdjust(nn.Module):
    
        def __init__(self, cls_num_list, tau=1, weight=None):
            super(LogitAdjust, self).__init__()
            cls_num_list = torch.cuda.FloatTensor(cls_num_list)
            cls_p_list = cls_num_list / cls_num_list.sum()
            m_list = tau * torch.log(cls_p_list)
            self.m_list = m_list.view(1, -1)
            self.weight = weight
    
        def forward(self, x, target):
            x_m = x + self.m_list
            return F.cross_entropy(x_m, target, weight=self.weight)


[ From:  https://github.com/FlamieZhu/Balanced-Contrastive-Learning/blob/main/loss/logitadjust.py ]
