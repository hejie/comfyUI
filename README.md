

# comfyUI集成stable-diffusion-3
![repository](https://images.squarespace-cdn.com/content/v1/6213c340453c3f502425776e/c24904d4-f0f0-4a26-9470-fec227dde15c/image-90.png?format=1500w)

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

1. Python 3.8+   查看 python -V
2. 因为一些原因，HuggingFace 在国内的访问时灵时不灵的，好在有社区爱好者做了一件很值得点赞的事情，使用 Caddy + CloudFlare 对 HuggingFace 做了镜像。
我们只需要在上面的下载命令前面加上一个环境变量就能够进行模型的下载啦：
```sh
echo 'export HF_ENDPOINT="https://hf-mirror.com"' >> ~/.bashrc
```
使其生效
```sh
source ~/.bashrc
```
###### 安装步骤

1. 安装 ComfyUI

克隆文件
```sh
git clone https://github.com/comfyanonymous/ComfyUI.git
```
安装依赖文件
```sh
pip install -r requirements.txt
```
启动
```sh
python main.py 或者 nohup python main.py  >/dev/null 2>p_error.log 2>&1 &
```
输出地址 [http://127.0.0.1:8188](http://127.0.0.1:8188)

2. 集成stable-diffusion-3-medium

  使用 HF 官方的 huggingface-hub CLI 程序下载模型
  ```sh
  pip install huggingface_hub[cli]
  ```
  使用专用的cli下载工具，能够实现断点续传，能够指定下载路径，更加方便我们对于模型资源的管理、硬件资源的使用
  ```sh

  huggingface-cli download stabilityai/stable-diffusion-3-medium sd3_medium_incl_clips_t5xxlfp8.safetensors --local-dir=./models/checkpoints/ --token xxx

  ```
  ### 注意
  由于模型发布者的版权的要求，部分模型无法公开访问下载，需要在 huggingface 上申请许可通过后，才可以下载。这类模型称之为 Gated Model。基本步骤是：
	* 1.申请许可
	* 2.获取 access token（获取地址：https://huggingface.co/settings/tokens)
	* 3.下载

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

- 推荐官方的 huggingface-cli 命令行工具

### 使用到的框架

- [stable-diffusion-3-medium](https://huggingface.co/stabilityai/stable-diffusion-3-medium)
- [hf-mirror](https://hf-mirror.com/)


### 作者
hj7.com@gmail.com



