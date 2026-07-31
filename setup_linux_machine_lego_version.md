# New Linux Machine Setup for Robotics Development

sudo apt update && sudo apt upgrade -y

sudo apt install -y git curl wget vim tmux btop htop tree unzip zip build-essential cmake pkg-config python3 python3-pip python3-venv python3-dev net-tools iproute2 dnsutils traceroute nmap openssh-client openssh-server ripgrep fd-find fzf bat jq ffmpeg vlc flameshot meshlab fastfetch python3-colcon-common-extensions python3-vcstool python3-rosdep

> A personal checklist and one-command bootstrap reference for setting up a fresh Linux workstation.

---

# System Update

```bash
sudo apt update && sudo apt upgrade -y
```

---

# Essential Development Tools

## Git

```bash
sudo apt install -y git
```

## Build Essentials

```bash
sudo apt install -y build-essential cmake pkg-config
```

## curl & wget

```bash
sudo apt install -y curl wget
```

## unzip / zip

```bash
sudo apt install -y unzip zip
```

---

# Editors

## VS Code

```bash
sudo snap install code --classic
```

or

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /usr/share/keyrings/packages.microsoft.gpg >/dev/null && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list && sudo apt update && sudo apt install -y code
```

---

## Vim

```bash
sudo apt install -y vim
```

---

# Terminal

## tmux

```bash
sudo apt install -y tmux
```

Clone personal configuration:

```bash
git clone <YOUR_TMUX_CONFIG_REPO> ~/.tmux
```

or

```bash
ln -sf ~/.tmux/.tmux.conf ~/.tmux.conf
```

---

# CLI Utilities

## btop (System Monitor)

```bash
sudo apt install -y btop
```

---

## htop

```bash
sudo apt install -y htop
```

---

## tree

```bash
sudo apt install -y tree
```

---

## ripgrep

```bash
sudo apt install -y ripgrep
```

---

## fd

```bash
sudo apt install -y fd-find
```

Create alias:

```bash
echo 'alias fd=fdfind' >> ~/.bashrc
```

---

## fzf

```bash
sudo apt install -y fzf
```

---

## bat

```bash
sudo apt install -y bat
```

Ubuntu alias:

```bash
mkdir -p ~/.local/bin && ln -s /usr/bin/batcat ~/.local/bin/bat
```

---

# Networking Tools

```bash
sudo apt install -y net-tools iproute2 dnsutils traceroute nmap openssh-client openssh-server
```

Useful commands:

```bash
ifconfig
ip addr
ping
ss
netstat
dig
```

---

# Python

```bash
sudo apt install -y python3 python3-pip python3-venv python3-dev
```

Upgrade pip

```bash
python3 -m pip install --upgrade pip
```

---

# Node.js (via nvm)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

Install latest LTS

```bash
nvm install --lts
```

---

# Rust

```bash
curl https://sh.rustup.rs -sSf | sh
```

---

# Docker

```bash
curl -fsSL https://get.docker.com | sh
```

Enable docker without sudo

```bash
sudo usermod -aG docker $USER
```

---

# GitHub CLI

```bash
(type -p wget >/dev/null || sudo apt install wget -y) && sudo mkdir -p -m755 /etc/apt/keyrings && wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg >/dev/null && sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list >/dev/null && sudo apt update && sudo apt install gh -y
```

---

# Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

---

# OpenAI Codex CLI (Optional)

```bash
npm install -g @openai/codex
```

---

# Robotics Development

## ROS 2

Install your preferred ROS 2 distribution.

Ubuntu 24.04:

- ROS 2 Jazzy

Ubuntu 22.04:

- ROS 2 Humble

Follow the official installation guide.

---

## colcon

```bash
sudo apt install -y python3-colcon-common-extensions
```

---

## vcstool

```bash
sudo apt install -y python3-vcstool
```

---

## rosdep

```bash
sudo apt install -y python3-rosdep
sudo rosdep init
rosdep update
```

---

# Simulation

## Gazebo

```bash
sudo apt install -y gazebo
```

or install Gazebo Harmonic/Ignition depending on ROS version.

---

# Visualization

```bash
sudo apt install -y meshlab
```

```bash
sudo apt install -y ffmpeg
```

---

# Desktop Applications

## Discord

```bash
sudo snap install discord
```

---

## Google Chrome

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb && sudo apt install ./google-chrome-stable_current_amd64.deb -y
```

---

## OBS Studio

```bash
sudo apt install -y obs-studio
```

---

## Flameshot

```bash
sudo apt install -y flameshot
```

---

## VLC

```bash
sudo apt install -y vlc
```

---

# Nice-to-have CLI Tools

```bash
sudo apt install -y jq
```

```bash
sudo apt install -y yq
```

```bash
sudo apt install -y silversearcher-ag
```

```bash
sudo apt install -y neofetch
```

or

```bash
sudo apt install -y fastfetch
```

---

# SSH

Generate a key

```bash
ssh-keygen -t ed25519 -C "gdteyuj123@gmail.com"
```

---

# Git Configuration

```bash
git config --global user.name "Your Name"
```

```bash
git config --global user.email "you@example.com"
```

```bash
git config --global init.defaultBranch main
```

---

# Useful Aliases

```bash
cat >> ~/.bashrc <<EOF

alias ll='ls -alF'
alias la='ls -A'
alias gs='git status'
alias gp='git pull'
alias gc='git commit'
alias tf='terraform'
alias cls='clear'
EOF
```

---

# Robotics Tools Worth Installing

- Foxglove Studio
- RViz2
- Gazebo Harmonic
- PlotJuggler
- Wireshark
- OpenCV
- Eigen3
- Ceres Solver
- GTSAM
- Open3D
- PCL (Point Cloud Library)
- librealsense
- Intel RealSense Viewer
- ZED SDK (if using ZED cameras)
- CUDA Toolkit (NVIDIA)
- Nsight Systems
- tmux-resurrect
- tmux-continuum

---

# Optional AI Development

```bash
pip install jupyterlab
```

```bash
pip install notebook
```

```bash
pip install numpy scipy matplotlib pandas
```

```bash
pip install torch torchvision
```

---

# Final Bootstrap

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install -y build-essential git curl wget vim tmux btop htop tree ripgrep fd-find fzf bat net-tools iproute2 dnsutils traceroute nmap openssh-client openssh-server python3 python3-pip python3-venv python3-dev python3-colcon-common-extensions python3-vcstool python3-rosdep cmake pkg-config jq yq ffmpeg vlc flameshot meshlab fastfetch
```

---

# After Installation Checklist

- [ ] Update system
- [ ] Install VS Code
- [ ] Install Chrome
- [ ] Install Discord
- [ ] Install Docker
- [ ] Install Node (nvm)
- [ ] Install Rust
- [ ] Install Claude Code
- [ ] Clone tmux config
- [ ] Clone dotfiles
- [ ] Setup SSH key
- [ ] Login GitHub
- [ ] Install ROS 2
- [ ] Install Gazebo
- [ ] Install Foxglove Studio
- [ ] Install CUDA (if NVIDIA)
- [ ] Install RealSense SDK (if needed)
- [ ] Configure Git
- [ ] Reboot
