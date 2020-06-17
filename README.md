
<!-- README.md is generated from README.Rmd. Please edit that file -->

# rumor\_detection\_2019\_ncov

<!-- badges: start -->

<!-- badges: end -->

The goal of rumor\_detection\_2019\_ncov is to …

1.  比赛官网: [疫情期间互联网虚假新闻检测](https://www.datafountain.cn/competitions/422)
2.  [数据集地址](https://www.datafountain.cn/competitions/422/datasets)
3.  GitBook:
    [notebook](https://jiaxiangbu.github.io/rumor_detection_2019_ncov/cookbook.html)

**赛题背景**

新型冠状病毒肺炎（COVID-19）疫情威胁着国民健康和社会秩序，准确、及时地向民众传达疫情相关信息对打赢这场人民战争至关重要。然而，一些疫情相关的虚假新闻也在互联网上广泛传播，给防疫工作有序开展带来了极大的阻碍。疫情期间，大蒜、土霉素、维生素C、单枞茶、胡柚、花椒水等二十多种食物、药品被传有预防或治疗新冠肺炎的作用，后被证实无科学依据。这些假新闻给民众科学防疫带来了显著的负面影响。在社交媒体上，疫情有关的虚假新闻内容更新快、扩散速度快，但人工审核存在滞后低效的问题，因此，开展自动化虚假新闻检测工作具有重要意义。
本赛题针对疫情相关虚假新闻检测中面临的两个实际问题：
一、检测时效性要求高。此次新冠肺炎疫情影响广泛，每一条新消息的发布都牵动着全国人们的心，虚假信息易造成爆炸性、病毒式传播。但在传播早期，其传播范围小，社会危害小。因此，对虚假信息进行早期检测并及时阻断其传播，可以极大降低虚假新闻带来的危害。
二、缺少专用数据。短时间内，难以得到训练模型需要的高质量的疫情相关新闻数据。但学术界在多年研究中，已积累了丰富的历史数据。将历史数据上训练的模型迁移到疫情相关新闻的真假检测上，有助于快速获得高性能的特定领域（时间）的检测模型。
本赛题由中国科学院计算技术研究所指导，旨在抑制本次疫情中虚假新闻的传播，营造清朗的网络舆论空间。

**[赛题任务](https://www.datafountain.cn/competitions/422)**

> 本次比赛提供多模态虚假新闻检测数据集，每条数据包括微博正文、评论、图片、所属领域等多个字段，包含三种类别，分别是无需判断，虚假新闻和真实新闻。训练集为和本次疫情无关的数据，评测集为和本次疫情相关的数据，要求参赛者将在其他领域学到的虚假新闻检测能力迁移到疫情领域中。同时，根据提供的评论时间进行划分，能越早进行进行检测的模型得分将越高。此外，本次比赛还提供一份疫情相关的辟谣数据集，可供灵活使用。

因此是一个多模态的多分类任务。

> 主要是通过分析图像和文本的 correlation，然后将图像和文本到同一空间(高德宏 2020)。

这里的多模态是提取图像和文本作为特征进行监督学习。

## 主要处理

1.  文本数据词向量化，LSTM
2.  图像数据 CNN 化
3.  加入了 attention 提高准确率

## 不足/待办

1.  图像没有加入 ResNet
2.  加入 TF hub 的例子

<h4 align="center">

**Code of Conduct**

</h4>

<h6 align="center">

Please note that the `rumor_detection_2019_ncov` project is released
with a [Contributor Code of
Conduct](https://github.com/JiaxiangBU/rumor_detection_2019_ncov/blob/master/CODE_OF_CONDUCT.md).<br>By
contributing to this project, you agree to abide by its terms.

</h6>

<h4 align="center">

**License**

</h4>

<h6 align="center">

CC0 ©
[李家翔,武睿琦,高文欣](https://github.com/JiaxiangBU/rumor_detection_2019_ncov/blob/master/LICENSE.md)

</h6>

<div id="refs" class="references">

<div id="ref-高德宏2020">

高德宏. 2020. “FashionBERT 电商领域多模态研究：如何做图文拟合？.” 天池大数据科研平台. 2020.
<https://mp.weixin.qq.com/s/UQYG4fUbrGVwNPOd7_xQ6Q>.

</div>

</div>
