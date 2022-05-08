# SAR图像CFAR检测的快速算法综述

**年份：2012
作者：赵明波，何俊，付强
出处：自动化学报
引用：Wang X, Li G, Plaza A, et al. Ship detection in SAR images via enhanced nonnegative sparse locality-representation of Fisher vectors[J]. IEEE Transactions on Geoscience and Remote Sensing, 2021, 59(11): 9424-9438.**

## 1. Summary

## 2. Research Objective(s)


## 3. Background / Problem Statement



## 4. Method(s)

## 5. Evaluation
  
## 6. Conclusionv

## 7. Notes(optional) 

## 8. References(optional) 


# ROC曲线
## 混淆矩阵
<!-- | 真实情况 |  |  预测结果|
| ---- | ---- | ---- |
| ^ | 正例 | 反例 |
| 正例 |  |  |
| ---- || |
| 反例 |

|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 | -->
<div style="text-align: center;">
<table style="margin: auto">
    <tr> 
        <td rowspan = "2">真实情况</td> 
        <td colspan="2"> 预测结果 </td> 
        <!-- <td>⾏1列3</td>  -->
   </tr>
    <tr>
    <td>正例</td> 
        <td>反例</td> 
        <!-- <td>⾏2列3</td>  -->
    </tr>
    <tr>
        <td>正例</td> 
        <td>TP（真正例）(目标检测为目标)</td> 
        <td>FN（假反例）(漏检)</td> 
    </tr>
    <tr>
        <td>反例</td> 
        <td>FP（假正例）(虚警)</td> 
        <td>TN（真反例）(海面)</td> 
    </tr>
</table>
</div>

## 查准率P和查全率R
$P = \frac{TP}{TP + FP}$
$R = \frac{TP}{TP + FN}$

## PR曲线
> 以查全率为横轴，查准率为纵轴做出的图像

* 如果一个学习器A的PR曲线被另外一个学习器B完全包住，则B的性能优于A；
* BEP(Break-Even P\oint) 平衡点，查准率 = 查全率时得到BEP，这时看哪个学习器的数值高即可断定性能优劣；
* F1度量：
$F_1 = \frac{2 * R * P}{P + R} = \frac{2 * TP}{样例总数 + TP - TN}$
* $F_\beta$ 度量
$F_\beta = \frac{(1 + \beta ^ 2) * P * R}{(\beta ^ 2 * P) + R}$
> 这里 $\beta$ 是用来度量P和R的相对重要性的，$\beta = 1$ 的时候，该标准为F1, $\beta > 1$ 的时候，查全率R影响更大，否则查准率P影响更大。

## ROC与AUC
> ROC曲线为以假正例率为横轴，真正例率为纵轴做出的图像。
> AUC为ROC曲线下面积。
> $AUC =  \frac{1}{2} \sum_{i=1}^{m-1}{(x_{i+1} - x_i) * (y_i + y_{i+1})}$
* 同理，被包住的曲线性能较低；
* 真正例率：
$TPR = \frac{TP}{TP + FN}$
* 假正例率:
$FPR = \frac{FP}{TN + FP}$


