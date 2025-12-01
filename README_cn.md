# 1. 搭建模型训练环境

在 Python=3.10 的环境下使用 Pytorch 训练：

```bash
conda create -n ImageFusion python=3.10 # 创建环境
conda activate ImageFusion # 进入环境
pip install -r requirements.txt # 下载 pytoch 等依赖包
```

# 2. 训练数据

Traceback (most recent call last):
  File "/home/lick/project/A-general-image-fusion-framework-using-multi-task-semi-supervised-learning/train_stage1.py", line 242, in <module>
    main()
  File "/home/lick/project/A-general-image-fusion-framework-using-multi-task-semi-supervised-learning/train_stage1.py", line 180, in main
    train_name_list = os.listdir(train_dir_f)
FileNotFoundError: [Errno 2] No such file or directory: '/home/wangwu/hybird_mfi/train/imageA/'

# 3. 开始训练

## 3.1 第一阶段训练

准备完 MFIF 和 MEIF 的训练数据后，执行命令：

```python
python train_stage1.py
```

### 重点关注：
1. train() 中的 loss 函数
2. test() 中的 评价指标

## 3.2 第二阶段训练

准备完 MFIF, MEIF 以及 IVF 的训练数据后，执行命令：

```
python train_stage2.py
```

### 重点关注：
1. train() 中的 loss 函数
2. test() 中的 评价指标

# Notes

1. 查看已经创建的 conda 环境：

```bash
conda env list
```

2. 查看 GPU 使用情况：

```bash
nvidia-smi
```