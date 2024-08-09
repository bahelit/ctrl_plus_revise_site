+++
title = "Install Ctrl+Revise"
weight = 2
description = """
This page tells you how to get started with Ctr+Revise.
"""
+++

### System Requirements:
8GB of VRAM (GPU) or 16GB of RAM (CPU)

### Prerequisites

##### Ollama
First ensure that you have `Ollama` installed.

You can download the latest release from the [Ollama.com](https://ollama.com/download) website.

Arch Linux users can install Ollama from the official repository.
{{< tabs "tabsId" >}}
{{< tab "AMD GPU" >}}
`sudo pacman -S ollama-rocm`
{{< /tab >}}
{{< tab "Nvidia GPU" >}}
`sudo pacman -S ollama-nvidia`
{{< /tab >}}
{{< tab "CPU" >}}
`sudo pacman -S ollama`
{{< /tab >}}
{{< /tabs >}}

###### Connect to Ollama
If you are running ollama on a different machine, you can connect to it by setting the environment variable `OLLAMA_HOST`
```bash
OLLAMA_HOST=http://<host-IP>:11434; ctrl_plus_revise
```

##### Docker (optional)
If users select to use [Docker](https://docker.com) to run Ollama, Ctrl+Revise will pull the latest Ollama Docker image and manage running it.

The official [Ollama Docker image](https://hub.docker.com/r/ollama/ollama) `ollama/ollama` is available on Docker Hub.

{{< tabs "tabsId" >}}
{{< tab "Docker command for AMD GPUs" >}}
`docker run -d --device /dev/kfd --device /dev/dri -v ollama:/root/.ollama -p 11434:11434 --name ollama --restart=always ollama/ollama:rocm`
{{< /tab >}}
{{< tab "Docker command for Nvidia GPUs" >}}
`docker run -d --gpus=all -v ollama:/root/.ollama -p 11434:11434 --restart=always --name ollama ollama/ollama`
{{< /tab >}}
{{< tab "Docker command for CPUs" >}}
`docker run -d -v ollama:/root/.ollama -p 11434:11434 --restart=always --name ollama ollama/ollama`
{{< /tab >}}
{{< /tabs >}}

{{< tip >}}
The Docker integration is disabled by default and can be enabled in the settings.
{{< /tip >}}

##### Xclip or Xsel (Linux only)
- [Xclip](https://github.com/astrand/xclip)
- [Xsel](http://www.vergenet.net/~conrad/software/xsel/)

`Xclip` or `Xsel` are used to interact with the clipboard on Linux systems. They are likely to be installed on your system already.
{{< tabs "tabsId" >}}
{{< tab "Arch" >}}
`sudo pacman -S xclip`

or

`sudo pacman -S xsel`
{{< /tab >}}
{{< tab "Ubuntu" >}}
`sudo apt install xclip`

or

`sudo apt install xsel`
{{< /tab >}}
{{< tab "Fedora" >}}
`sudo dnf instal xclip`

or

`sudo dnf instal xsel`
{{< /tab >}}
{{< /tabs >}}

## Run Ctrl+Revise

Use the installer or compile the project from source.

### Option 1 (recommended)

Download the latest release from the [releases page](https://github.com/bahelit/ctrl_plus_revise/releases).

#### Windows
Run the [CtrlPlusRevise-Installer-Window-amd64.exe](https://github.com/bahelit/ctrl_plus_revise/releases/download/v0.0.7/CtrlPlusRevise-Installer-Window-amd64.exe) file and follow the instructions.

#### Linux
The Linux binary will Launch Ctrl+Revise from any directory it is located in. 
```bash
chmod +x ctrl_plus_revise-linux-amd64
```

The tar file includes a Makefile designed to manage the installation process of the Ctrl+Revise application. It includes targets for user-install (no sudo required), system install, and uninstall.

**Targets**
The following targets are available in the Makefile:
```bash
tar -xvf Ctrl+Revise.tar.xz # Extracts the tar file.
make install # Installs the application in the system's default location.
make uninstall # Uninstalls the application from the system.
make user-install # Installs the application in the user's local directory (~/.local/).
make user-uninstall # Uninstalls the application from the user's local directory.
```

#### MacOS
No builds at this time, MacBook screen is currently broke.
Follow the build from source instructions.

### Option 2 (build from source)

This option lets you get the latest changes. First things first, ensure you have `go` [installed on your machine](https://golang.org/doc/install).

#### Windows
Please follow the Getting Started guide from the Fyne documentation [here](https://docs.fyne.io/started/) to setup MSYS2 and compile from within the MingW-w64 window.

#### MacOS
Set up the Xcode command line tools by opening a Terminal window and typing the following:

`xcode-select --install`

#### Linux
Find the list of dependencies for your distro in the Fyne documentation [here](https://docs.fyne.io/started/)

##### Compile
To start the project run the following command:
```bash
git clone https://github.com/bahelit/ctrl_plus_revise.git
cd ctrl_plus_revise
go run .
```
