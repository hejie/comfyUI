

# comfyUI集成stable-diffusion-3


## 目录

- [上手指南](#上手指南)
  - [开发前的配置要求](#开发前的配置要求)
  - [安装步骤](#安装步骤)
- [文件目录说明](#文件目录说明)
- [部署](#部署)
- [使用到的框架](#使用到的框架)
- [作者](#作者)

### 上手指南

###### 开发前的配置要求

1. 云部署

###### **安装步骤**

1. 查看python -V
2. Clone the repo

```sh
克隆文件
git clone https://github.com/comfyanonymous/ComfyUI.git

安装依赖文件
pip install -r requirements.txt

启动
python main.py 或者 nohup python main.py  >/dev/null 2>p_error.log 2>&1 &

```
输出地址 [http://127.0.0.1:8188](http://127.0.0.1:8188)

### 文件目录说明
eg:

```
filetree 
├── README.md
├── /docs/
│  ├── /rules/
│  │  ├── backend.txt
│  │  └── frontend.txt
├── /static/
├── /templates/
└── /util/
```


### 部署

暂无

### 使用到的框架

- [stable-diffusion-3-medium](https://huggingface.co/stabilityai/stable-diffusion-3-medium)
- [hf-mirror](https://hf-mirror.com/)


### 作者
hj7.com@gmail.com



