# 第十九届“挑战杯”揭榜挂帅专项赛·华为赛道初赛指导手册

## 前言

本文将帮助大家快速上手比赛，指引大家如何使用ModelArts平台帮助你做实验、存数据、训模型、跑结果。

请注意，本次比赛涉及到的所有OBS、ModelArts等资源都应在<span style="color:rgb(216,27,68)">**贵阳一**</span>区域下运行：

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/1702d301-a17a-4555-b0c6-96fc1181e31c.png)

## 快速导航

这部分将给大家提供常用网页的链接，快速一键转跳。

- [比赛主页](https://competition.huaweicloud.com/information/1000042047/introduction)

- [ModelArts控制台](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2#/dashboard)

- [OBS对象存储服务](https://console.huaweicloud.com/console/?region=cn-southwest-2#/obs/manager/dashboard)

- [模型包官方文档](https://support.huaweicloud.com/inference-modelarts/inference-modelarts-0055.html)

## ModelArts全局配置

在ModelArts上使用Notebook、OBS存储服务、训练作业等等很多功能，都需要你先进行访问授权。[点此进入ModelArts控制台](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2#/dashboard)，按照下图操作即可。

![image.png](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/0ecfaadb-4cec-4458-b8ed-eb69b589c8fd.png)

## 使用Notebook

我们通过Notebook提供了详尽的教程，以我们的Baseline代码为例子，指导选手们完成自己模型的训练、推理流程。

Notebook包括：

1. 模型训练：数据准备、模型训练、模型验证

2. 构建比赛AI应用：AI应用开发与验证、构建AI应用

当然这一步不是必须的，选手如果比较熟悉ModelArts平台，可以自行创建训练、推理任务。

### 模型训练

1. 根据初赛要求，选手需基于AI芯片昇腾910、AI应用开发平台ModelArts等华为昇腾云AI技术，因此Baseline的数据准备、模型训练和模型验证部分，在昇腾910环境下进行，对应我们提供了[Notebook-Ascend](https://authoring-modelarts-cnnorth4.huaweicloud.com/console/lab?share-url-b64=aHR0cHM6Ly9kdHNlLW1vZGVsLWd1aXlhbmd5aS5vYnMuY24tc291dGh3ZXN0LTIubXlodWF3ZWljbG91ZC5jb20vY2FzZV96b28vMjAyNFRaQi9iYXNlbGluZS9yb3VuZDEvUENCX2RldGVjdC5pcHluYg==)，您可以对Notebook进行简单浏览或右击文件进行下载：

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/9c3817e0d61d458b89cbf1501bedba76.jpg)

2. 如需使用Notebook-Ascend，请点击[此处](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2&locale=zh-cn#/dev-container)，进入ModelArts的开发环境，点击创建：

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/92e287502fe84aef9cf7f778e6f35161.png)

在创建notebook页面，按照如下参数进行配置：

名称：notebook-yolov5（可自定义）

自动停止：开启，1小时

镜像：“公共镜像”，选择“pytorch_1.11.0-cann_6.3.2-py_3.7-euler_2.10.7-aarch64-snt9b”

资源类型：公共资源池

类型：Ascend

规格：Ascend: 1*ascend-snt9b|ARM: 24核 192GB

存储配置：云硬盘EVS，20G

SSH远程开发：不开启

点击“立即创建”，确认产品规格后点击“提交”，并返回。

注：notebook创建完毕后，存储会持续产生少量费用（无论是否运行），代金券使用场景覆盖存储。

3. 进入到notebook页面后，可以将前面下载的notebook拖动到notebook的文件栏中，双击打开运行。

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/410068432ee747c299e8acef8b99d2d5.jpg)

然后就可以根据notebook里提供的详细教程，完成模型的训练开发。

### 构建比赛AI应用

1. 根据初赛要求，选手提交的AI应用，将采用CPU规格进行推理，并最终将推理结果进行判分。因此AI应用开发与验证、构建AI应用部分可以在CPU环境下运行，对应我们提供了[Notebook-CPU](https://authoring-modelarts-cnnorth4.huaweicloud.com/console/lab?share-url-b64=aHR0cHM6Ly9kdHNlLW1vZGVsLWd1aXlhbmd5aS5vYnMuY24tc291dGh3ZXN0LTIubXlodWF3ZWljbG91ZC5jb20vY2FzZV96b28vMjAyNFRaQi9iYXNlbGluZS9yb3VuZDEvUENCX2RldGVjdF9jcHUuaXB5bmI=)，您可以对Notebook进行简单浏览或右击文件进行下载：

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/41589cf971a142b9acf84cf38e84e1e8.jpg)

2. 如需使用Notebook-CPU，请点击[此处](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2&locale=zh-cn#/dev-container)，进入ModelArts的开发环境，点击创建：

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/05d7459af32a4300b75e17c7c8ecdd3f.png)

在创建notebook页面，按照如下参数进行配置：

名称：notebook-yolov5-deploy（可自定义）

自动停止：开启，1小时

镜像：“公共镜像”，选择“pytorch1.8-cuda10.2-cudnn7-ubuntu18.04”

资源类型：公共资源池

类型：CPU

规格：CPU: 2核 8GB

存储配置：云硬盘EVS，20G

SSH远程开发：不开启

点击“立即创建”，确认产品规格后点击“提交”，并返回。

注：notebook创建完毕后，存储会持续产生少量费用（无论是否运行），代金券使用场景覆盖存储。

3. 进入到notebook页面后，可以将前面下载的notebook拖动到notebook的文件栏中，双击打开运行。

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/410068432ee747c299e8acef8b99d2d5.jpg)

然后就可以根据notebook里提供的详细教程，完成模型的AI应用开发。

如果你已经运行完notebook之后，可以跳过以下几个步骤，直接创建在线服务。

## 使用OBS桶进行储存管理

模型代码，权重文件，数据集，都可以上传至OBS中，方便在训练任务、部署推理服务等操作时使用。

1. [点此进入OBS对象存储服务](https://console.huaweicloud.com/console/?region=cn-southwest-2#/obs/manager/dashboard)

2. 创建桶

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/9f49a6b7-5ad0-48cd-aa0d-446e14a44691.png)

名称可以自定义，区域选择**贵阳一**，其他设置可以保持默认或按需修改

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/b7c532bc-32d4-422c-80ea-7f4a1ff468b4.png)

3. 创建好以后点击进入桶

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/74802b84-94fe-4481-9b5e-12d91e2293b6.png)

4. 点击左侧“对象”进入桶的文件列表，就可以上传文件了

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/db3cca87-dd43-4a51-afd7-c2937b14652f.png)

**注意**，网页版的OBS服务功能有限，同时只能上传100个文件，且上传好的文件不支持移动、重命名，所以请预先在本地调整好目录结构再上传，如果上传文件超过100个，请分批上传或直接压缩打包后上传（也可以使用OBS Browser+进行上传，一次能上传500个文件，点击[此处](https://developer.huaweicloud.com/tools#section-1)下载OBS Browser+）。

## 制作数据集

本次大赛提供训练[样例数据](https://dtse-model-guiyangyi.obs.cn-southwest-2.myhuaweicloud.com/dataset/2024TZB/PCB样例集.zip)，选手可以参考格式，自行收集整理数据。

## 使用ModelArts创建推理应用

最终在提交推理代码时，需要根据官方文档准备好一个模型包，请[点击此处](https://support.huaweicloud.com/inference-modelarts/inference-modelarts-0055.html)查看文档，或者查看使用Notebook这一章节内容，里面有详细介绍如何完成一个模型包（即使你不使用该notebook来训练和推理，也可以参考里面的内容）。

当模型包准备好以后：

1. 请[点击此处](https://console.huaweicloud.com/console/?region=cn-southwest-2#/obs/manager/dashboard)，进入OBS桶，然后按照要求上传模型包;

2. 请[点击此处](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2#/myModel)，进入ModelArts的AI应用管理界面，点击“创建”。

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/0b8136eae7b64639bcae119b5e514ad2.png)

配置参数参考下图：

名称：自定义，如model-yolov5

版本：默认

元模型来源：从对象存储服务（OBS）中选择

选择元模型：点击右侧文件图标，选择刚刚模型包代码上传的OBS桶路径（若想体验前面baseline中的模型，则需要将baseline的代码传到自己的OBS桶内，此处填入OBS桶代码目录下的Yolov5_for_PyTorch/infer文件夹）

其余参数：保持默认

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/1dbc4c3db538483d9e113de4d7a6d002.png)

3. 创建需要花一些时间，创建完成后状态会变为“正常”。

4. 注意：运行时依赖 必须是配置文件中编写自动填充的，自己在页面上额外添加，是无法上传至比赛后台的。

## 基于创建的AI应用部署为在线服务

这一步主要是为了检验模型包是否正确，可以将创建的AI应用部署为一个在线服务，在线预测和调试，从而确认模型包是正常可用的。大赛后台使用的是批量部署，你也可以尝试批量部署服务，在一定量的数据上测试得分。

1. 请[点击此处](https://console.huaweicloud.com/modelarts/?region=cn-southwest-2#/real-time)，进入在线服务部署界面，然后点击“部署”进行服务部署。

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/fcaaf90b-be78-481b-b0ab-79adf98d4168.png)

资源池选择**公共资源池**，AI应用选择**上一步创建的AI应用**，计算节点规格选择**CPU: 2 核 8GB**，点击**下一步**进行创建

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/3067e7e3e28e48af948c97d210a97c08.png)

2. 等部署完成后，就可以进行在线预测，服务调用可以参考[使用文档](https://support.huaweicloud.com/inference-modelarts/inference-modelarts-0023.html)。

![image](https://lab.huaweicloud.com/sandbox-base-path/nbyxcvjpvd/step-path/69c7a24a260746be9e30395c8252bc43.jpg)

**注意：**按照比赛要求的推理结果输出后，如果检测到目标，在左侧的图片上会显示检测到的目标类别、置信度和位置。


## 提交模型包进行判分

如果上述准备你已经全部完成，请[点击此处](https://console.huaweicloud.com/console/?region=cn-southwest-2#/obs/manager/dashboard)进入AI应用界面，找到已经经过在线服务测试过的应用包，进行发布：

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhuaweicloud.com/meta/publicImage/0a206e6c-9c82-4c3d-b7a7-b6241048bf20.png)

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/ec52948b-47af-451c-a59a-5ec6810bdcc3.png)

提交完成后，判分结果将会以邮件形式发送给你。（如果你的模型包输出未按照我们的格式要求，可能会导致判分失败；如果你的模型包本身结构有问题，后台判分时可能会直接部署失败。）

## 资源释放

使用完ModelArts相关计算资源后，请务必及时释放资源，否则会造成资源浪费甚至账号欠费。

ModelArts以下模块会涉及云资源的消耗并会按需或按周期产生费用：自动学习，Notebook实例，训练作业，TensorBoard，在线服务。使用完需要“停止”自动学习、Notebook、TensorBoard、在线服务。

停止所有需消耗云资源的作业后，可在ModelArts总览页面确认所有计费项都为“0”。

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/adcc84c1-0d48-42f9-98e7-66732b92f42a.png)

<span style="color:rgb(216,27,68)">删除OBS桶</span>

由于OBS存储会收费，请务必执行这一步

点击[此处](https://console.huaweicloud.com/console/?region=cn-southwest-2#/obs/manager/buckets)，进入OBS控制台查看OBS桶，点击对应桶名，进入桶内，点击对象，全选，删除文件夹：

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/aef78d59-30b1-4331-b09f-9dc6f7ea11e1.png)

回退至桶列表，即可删除OBS桶：

![](https://cnnorth4-modelhub-media.obs.cn-north-4.myhwclouds.com/meta/publicImage/60a93b49-1b0b-4e07-bd86-ce6668c62cf3.png)

**注意**：公有云的按需使用是采用后付费模式，即先使用再付费，一个小时会出一次话单，比如：2019.6.24  04:00~05:00这段时间使用的费用，在05:00时刻采集完成后，才会出话单，进行扣费。
