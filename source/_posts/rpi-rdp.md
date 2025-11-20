---
title: '树莓派 rdp 云电脑搭建'
date: 2025-11-14 11:59:31
tags: hardware
category: Blog
---

如何使用 KDE 和 xrdp 在树莓派搭建云电脑（AI 文章）

<!-- more -->

在树莓派上安装 **KDE Plasma 桌面**并通过 **RDP 协议**实现无显示器远程访问，可按以下步骤操作：

### **一、安装 KDE Plasma 桌面**

1. **更新系统**  
   在树莓派终端执行：

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. **安装 KDE Plasma 桌面环境**  
   Raspberry Pi OS 基于 Debian，需安装 `kde-standard` 或完整版 `kde-full`（后者包含更多应用）：

   ```bash
   sudo apt install kde-standard -y
   ```

   - **注意**：KDE Plasma 需要 **64 位系统**支持。若使用 32 位 Raspberry Pi OS，需更换为 64 位版本（Raspberry Pi OS 64-bit）。

3. **配置自动登录（可选）**  
   若需跳过登录界面直接进入桌面：

   ```bash
   sudo raspi-config
   ```

   选择 **System Options → Boot / Auto Login → Desktop Autologin**。

   注意：操作可能因版本而异

### **二、安装 RDP 服务（xrdp）**

1. **安装 xrdp**  
   xrdp 是开源 RDP 服务器，兼容 Windows 远程桌面：

   ```bash
   sudo apt install xrdp -y
   ```

2. **解决依赖冲突（可选）**  
   仅当提升项目缺失时执行，否则无需操作：若提示未安装 `tightvncserver`：

   ```bash
   sudo apt install tightvncserver xrdp -y
   ```

3. **启动 xrdp 服务**  

   ```bash
   sudo systemctl enable xrdp && sudo systemctl start xrdp
   ```

### **三、配置网络与防火墙**

1. **查看树莓派 IP 地址**  

   ```bash
   hostname -I
   ```

   记录输出的 IP（如 `192.168.x.x`）。

2. **允许 RDP 端口（3389）通过防火墙**  
   Raspberry Pi OS 默认无防火墙，若启用 `ufw`：

   ```bash
   sudo ufw allow 3389/tcp
   ```

### **四、远程连接**

1. **Windows 客户端连接**  
   - 按 `Win + R`，输入 `mstsc` 打开远程桌面连接。
   - 输入树莓派 IP 地址，点击连接。
   - 输入树莓派用户名和密码（默认为 `pi`/`raspberry`，建议修改）。

2. **Linux/macOS 客户端连接**  
   - 使用 `Remmina` 或 `FreeRDP`：

     ```bash
     sudo apt install remmina  # Debian/Ubuntu
     remmina                   # 启动并配置 RDP 连接
     ```

### **五、优化与故障排除**

1. **KDE Plasma 性能优化**  
   - **禁用混成器（Compositor）**：  
     按 `Alt + Shift + F12` 临时关闭，或通过系统设置永久禁用（路径：`System Settings → Display and Monitor → Compositor`）。
   - **使用轻量级主题**：  
     在 `System Settings → Appearance` 中选择简洁主题（如 `Breeze`）。

2. **常见问题解决**  
   - **连接失败**：  
     - 检查树莓派 IP 是否变化（重启路由器可能导致 IP 变更）。
     - 确认 `xrdp` 服务运行：

       ```bash
       sudo systemctl status xrdp
       ```

   - **黑屏/卡顿**：  
     - 降低分辨率：在 RDP 客户端设置中调整。
     - 更换桌面环境：若 KDE 性能不足，可改用 Xfce 或 LXQt：

       ```bash
       sudo apt install xfce4 xfce4-terminal -y
       ```

3. **安全建议**  
   - **修改默认密码**：

     ```bash
     passwd pi
     ```

   - **禁用 SSH 密码登录（改用密钥）**：  
     编辑 `/etc/ssh/sshd_config`，设置 `PasswordAuthentication no`。

### **六、完整命令清单**

```bash
# 更新系统
sudo apt update && sudo apt upgrade -y

# 安装 KDE Plasma（64 位系统）
sudo apt install kde-standard -y

# 安装 xrdp
sudo apt install xrdp -y

# 启动 xrdp 服务
sudo systemctl enable xrdp && sudo systemctl start xrdp

# 允许 RDP 端口（可选）
sudo ufw allow 3389/tcp

# 查看 IP 地址
hostname -I
```

### **总结**

通过上述步骤，你可在无显示器情况下，通过 RDP 协议远程访问树莓派的 KDE Plasma 桌面。若遇到性能问题，可切换至轻量级桌面环境或优化 KDE 设置。
