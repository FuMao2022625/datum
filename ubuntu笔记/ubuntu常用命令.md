Ubuntu 是基于 Debian 的 Linux 发行版，其核心命令与通用 Linux 命令高度一致。为了方便你查找，我将常用命令按功能模块分类整理如下：

### 一、 文件与目录管理

| 命令 | 用法说明 | 常用示例 |
| :--- | :--- | :--- |
| `ls` | 列出目录内容 | `ls -la` (显示所有文件，含隐藏文件及详细信息) |
| `cd` | 切换目录 | `cd /home/user/Documents` |
| `pwd` | 显示当前工作目录的绝对路径 | `pwd` |
| `mkdir` | 创建新目录 | `mkdir -p dir1/dir2/dir3` (递归创建) |
| `rm` | 删除文件或目录 | `rm -rf dirname` (递归且强制删除，**慎用！**) |
| `cp` | 复制文件或目录 | `cp -r source_dir/ target_dir/` (递归复制) |
| `mv` | 移动或重命名文件/目录 | `mv old_name new_name` |
| `touch` | 创建空文件或更新时间戳 | `touch newfile.txt` |
| `find` | 在文件系统中搜索文件 | `find /home -name "*.txt"` (按名字查找) |
| `cat` | 查看文件内容 | `cat file.txt` |
| `less`/`more` | 分页查看大文件 | `less longfile.log` (按 `q` 退出) |
| `head`/`tail` | 查看文件头/尾几行 | `tail -f /var/log/syslog` (实时跟踪日志) |
| `chmod` | 修改文件权限 | `chmod +x script.sh` (添加可执行权限) |
| `chown` | 修改文件所有者 | `sudo chown user:group file.txt` |
| `tar` | 压缩/解压归档文件 | `tar -czvf archive.tar.gz folder/` (创建)；`tar -xzvf archive.tar.gz` (解压) |

### 二、 系统状态与进程管理

| 命令 | 用法说明 | 常用示例 |
| :--- | :--- | :--- |
| `ps` | 显示当前进程快照 | `ps aux` (查看所有进程详细信息) |
| `top` / `htop` | 实时显示进程列表（htop更友好） | `htop` (如未安装：`sudo apt install htop`) |
| `kill` | 终止进程 | `kill -9 PID` (强制杀死进程) |
| `df` | 显示磁盘空间使用情况 | `df -h` (以人类可读格式显示) |
| `du` | 统计文件/目录的磁盘使用量 | `du -sh folder/` (显示目录总大小) |
| `free` | 显示内存使用情况 | `free -h` |
| `uname` | 查看系统内核信息 | `uname -a` |
| `uptime` | 查看系统运行时间 | `uptime` |
| `dmesg` | 查看内核环缓冲区消息（硬件启动日志） | `dmesg | grep error` |
| `service` / `systemctl` | 管理系统服务 | `sudo systemctl status sshd` (查看SSH服务状态) |

### 三、 软件包管理 (APT)

Ubuntu 使用 APT 包管理器，几乎所有软件安装都通过它完成。

| 命令 | 用法说明 |
| :--- | :--- |
| `sudo apt update` | 更新软件包列表（必须首先执行） |
| `sudo apt upgrade` | 升级所有已安装的可更新软件包 |
| `sudo apt full-upgrade` | 更全面的升级，可能处理依赖变化 |
| `sudo apt install <package>` | 安装指定软件包 |
| `sudo apt remove <package>` | 卸载软件包（保留配置文件） |
| `sudo apt purge <package>` | 彻底卸载（删除配置文件） |
| `sudo apt autoremove` | 自动删除不再需要的依赖包 |
| `apt search <keyword>` | 搜索可用的软件包 |
| `apt show <package>` | 显示软件包的详细信息 |

### 四、 用户与权限管理

| 命令 | 用法说明 | 常用示例 |
| :--- | :--- | :--- |
| `sudo` | 以超级用户权限执行命令 | `sudo apt update` |
| `whoami` | 显示当前用户名 | `whoami` |
| `id` | 显示当前用户ID和组ID | `id` |
| `adduser` | 添加新用户（推荐） | `sudo adduser newuser` |
| `usermod` | 修改用户账户 | `sudo usermod -aG sudo newuser` (将用户加入sudo组) |
| `passwd` | 修改当前用户密码 | `passwd` |
| `su` | 切换用户 | `su - username` |
| `groups` | 显示用户所属的组 | `groups username` |

### 五、 网络相关

| 命令 | 用法说明 | 常用示例 |
| :--- | :--- | :--- |
| `ping` | 测试网络连通性 | `ping google.com` (按 Ctrl+C 停止) |
| `ifconfig` | 查看/配置网络接口（部分系统已弃用） | `ip addr` (推荐替代) |
| `ip` | 强大的网络配置工具 | `ip addr`, `ip route` |
| `ss` | 查看网络套接字统计 | `ss -tuln` (查看正在监听的TCP/UDP端口) |
| `netstat` | 网络统计（需安装：`sudo apt install net-tools`） | `netstat -an` |
| `wget` / `curl` | 下载文件或发送HTTP请求 | `wget http://example.com/file.zip` |
| `ssh` | 远程登录到另一台机器 | `ssh user@192.168.1.100` |

### 六、 其他实用命令

| 命令 | 用法说明 | 常用示例 |
| :--- | :--- | :--- |
| `grep` | 在文件或输出中搜索文本 | `grep "error" logfile.txt` |
| `echo` | 输出字符串或变量 | `echo $HOME` |
| `alias` | 设置命令别名 | `alias ll='ls -la'` |
| `history` | 查看命令行历史记录 | `history` |
| `shutdown` | 关机或重启 | `sudo shutdown now` (立即关机)；`sudo reboot` (重启) |
| `clear` | 清屏 | `clear` |
| `man` | 查看命令的详细帮助手册 | `man ls` (按 `q` 退出) |

### 快速提示

1. **`Tab` 键自动补全**：输入命令、文件名或路径时，按 `Tab` 可以自动填充。
2. **`Ctrl + C`**：终止当前正在运行的命令。
3. **`Ctrl + D`**：退出当前 shell 或注销。
4. **`Ctrl + R`**：向后搜索你输入过的历史命令。
5. **管道 `|`**：将前一个命令的输出作为后一个命令的输入。
    - 例如：`ps aux | grep python`（查找所有 Python 进程）。

---

以上是 Ubuntu 日常使用中最核心的命令。如果你对某个具体命令有疑问，或者需要处理某个具体任务（如配置网络、设置定时任务等），可以告诉我，我会给出更详细的步骤。