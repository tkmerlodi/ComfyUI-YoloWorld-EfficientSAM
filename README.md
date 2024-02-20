
![ywes_](https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/assets/140084057/fff48236-8feb-48d6-946e-ba429111427f)


# ComfyUI YoloWorld-EfficientSAM

Unofficial implementation of [YOLO-World + EfficientSAM](https://huggingface.co/spaces/SkalskiP/YOLO-World) & [YOLO-World](https://github.com/AILab-CVC/YOLO-World) for ComfyUI


![Dingtalk_20240220201311](https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/assets/140084057/765c7b7b-1224-48f1-8a98-d05d438304d0)


## 项目介绍 | Info

- 对[YOLO-World + EfficientSAM](https://huggingface.co/spaces/SkalskiP/YOLO-World)的非官方实现

- 利用全新的 [YOLO-World](https://github.com/AILab-CVC/YOLO-World) 与 [EfficientSAM](https://github.com/yformer/EfficientSAM) 实现高效的对象检测 + 分割
  
- 版本：V1.0 同时支持图像与视频，还支持输出 mask 蒙版


# 视频演示


https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/assets/140084057/ed51a9c7-0e06-4026-8946-04dd78aa712c



## 节点说明 | Features

- YOLO-World 模型加载 | 🔎Yoloworld Model Loader
    - 支持 3 种官方模型：yolo_world/l, yolo_world/m, yolo_world/s，会自动下载并加载
    
- EfficientSAM 模型加载 | 🔎ESAM Model Loader
    - 支持 CUDA 或 CPU
    
- 检测 + 分割 | 🔎Yoloworld ESAM
    - yolo_world_model：接入 YOLO-World 模型
    - esam_model：接入 EfficientSAM 模型
    - image：接入图像
    - categories：检测 + 分割内容
    - confidence_threshold：置信度阈值，降低可减少误检，增强模型对所需对象的敏感性。增加可最小化误报，防止模型识别不应识别的对象
    - iou_threshold：IoU 阈值，降低数值可减少边界框的重叠，使检测过程更严格。增加数值将会允许更多的边界框重叠，适应更广泛的检测范围
    - box_thickness：检测框厚度
    - text_thickness：文字厚度
    - text_scale：文字缩放
    - with_segmentation：是否开启 EfficientSAM 进行实例分割
    - with_confidence：是否显示检测对象的置信度
    - with_class_agnostic_nms：是否抑制类别之间的重叠边界框

![Dingtalk_20240220175722](https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/assets/140084057/17b106a2-9b7f-4534-ae3d-b1e97501bc2e)

 
## 安装 | Install

- 推荐使用管理器 ComfyUI Manager 安装（On the Way）

- 手动安装：
    1. `cd custom_nodes`
    2. `git clone https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM`
    3. `cd custom_nodes/ComfyUI-YoloWorld-EfficientSAM`
    4. `pip install -r requirements.txt`
    5. 重启 ComfyUI

- 模型下载：将 [EfficientSAM](https://huggingface.co/camenduru/YoloWorld-EfficientSAM/tree/main) 中的 efficient_sam_s_cpu.jit 和 efficient_sam_s_gpu.jit 下载到 custom_nodes/ComfyUI-YoloWorld-EfficientSAM 中


## 工作流 | Workflows

[V1.0 图片检测+分割](https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/blob/main/YOLO_World_EfficientSAM_WORKFLOWS/YoloWorld-EfficientSAM%20V1.0%20IMG%20%E3%80%90Zho%E3%80%91.json)


[V1.0 视频检测+分割](https://github.com/ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM/blob/main/YOLO_World_EfficientSAM_WORKFLOWS/YoloWorld-EfficientSAM%20V1.0%20VIDEO%20%E3%80%90Zho%E3%80%91.json)


## 更新日志

- 20240220

  创建项目

  V1.0 同时支持图像与视频的检测与分割，还支持输出 mask 蒙版


## Stars 

[![Star History Chart](https://api.star-history.com/svg?repos=ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM&type=Date)](https://star-history.com/#ZHO-ZHO-ZHO/ComfyUI-YoloWorld-EfficientSAM&Date)


## Credits

[YOLO-World + EfficientSAM](https://huggingface.co/spaces/SkalskiP/YOLO-World)

[YOLO-World](https://github.com/AILab-CVC/YOLO-World)

[EfficientSAM](https://github.com/yformer/EfficientSAM)

代码还参考了 [@camenduru](https://twitter.com/camenduru) 感谢！
