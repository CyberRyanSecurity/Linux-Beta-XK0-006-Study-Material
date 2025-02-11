# Linux-Beta-XK0-006-Study-Material
Hey all - I decided to purchase the Linux+ Beta Exam and listed below will be all study materials based on the objectives provided by CompTIA - Hope this helps 

URL for Exams under Development: https://www.comptia.org/training/resources/exam-objectives/exam-objectives-under-development

Linux+ Beta XK0-006 Objectives 👍- https://comptiacdn.azureedge.net/webcontent/docs/default-source/exam-objectives/under-development/draft-linux-xk0-006-exam-objectives-(1-0).pdf?sfvrsn=a14831f9_6

**1.1 Explain basic Linux concepts**
### **1. Basic Boot Process**

The boot process is critical for initializing and starting the Linux operating system.

- **Bootloader:**
    - **Purpose:** The bootloader initializes the hardware and loads the kernel into memory.
    - **Examples:** GRUB (GNU GRUB), LILO.
    - **Configuration Files:** Found in `/boot/grub/grub.cfg` or `/etc/default/grub`, these files define settings such as the default kernel, timeout, and boot options.
    - **Key Commands:**
        - `update-grub`: Updates GRUB configuration.
        - `grub-install`: Installs the GRUB bootloader.
- **Kernel:**
    - **Definition:** The kernel is the core of the Linux OS, managing hardware, memory, and processes.
    - **Boot Parameters:** Options passed to the kernel during boot to modify behavior (e.g., `ro`, `quiet`, `single`).
    - **File Location:** Typically located in `/boot/vmlinuz-*`.
- **Initial RAM Disk (initrd):**
    - **Purpose:** A temporary filesystem loaded into RAM to prepare the system to mount the real root filesystem.
    - **Files:** Typically named `/boot/initrd.img-*`.
    - **Command:** `mkinitramfs` to generate initrd images.
- **Preboot Execution Environment (PXE):**
    - **Function:** Allows a computer to boot from a network server without local storage.
    - **Common Use:** Diskless systems or mass deployments.
    - **Tools:** `dnsmasq` for PXE boot setup.
 
### **2. Filesystem Hierarchy Standard (FHS)**

The FHS defines the structure and purpose of directories in Linux. Key directories include:

- **`/`:** Root of the filesystem, containing all other directories.
- **`/bin`:** Essential user binaries (e.g., `ls`, `cp`, `mv`).
- **`/boot`:** Bootloader files, kernel images, and initrd images.
- **`/dev`:** Device files representing hardware (e.g., `/dev/sda` for disks).
- **`/etc`:** Configuration files for the system and applications.
- **`/home`:** User-specific data and configuration (e.g., `/home/user`).
- **`/lib`:** Libraries essential for binaries in `/bin` and `/sbin`.
- **`/proc`:** Virtual filesystem providing kernel and process information.
- **`/sbin`:** System binaries for administrators (e.g., `reboot`, `iptables`).
- **`/tmp`:** Temporary files that are cleared on reboot.
- **`/usr`:** Secondary hierarchy for user applications, libraries, and binaries.
- **`/var`:** Variable files, including logs (`/var/log`), cache (`/var/cache`), and spool files (`/var/spool`).

 ### **3. Server Architectures**

Linux supports multiple hardware architectures, enabling flexibility in deployment:

- **AArch64:**
    - 64-bit ARM architecture.
    - Common in energy-efficient devices, such as smartphones and servers (e.g., Raspberry Pi).
- **RISC-V:**
    - Open-source, scalable architecture.
    - Focuses on simplicity and energy efficiency; increasingly popular in research and IoT devices.
- **x86:**
    - 32-bit architecture found in legacy PCs.
    - Limited memory addressing (up to 4 GB).
- **x86_64/AMD64:**
    - 64-bit architecture.
    - Supports larger memory (over 4 GB) and more efficient processing.
    - Standard in modern servers and desktops. 

### **4. Linux Distributions**

Linux distributions bundle the kernel with utilities, libraries, and package management tools.

- **RPM-Based:**
    - Uses RPM (Red Hat Package Manager) for package management.
    - Examples:
        - **Red Hat Enterprise Linux (RHEL):** Enterprise-focused with support.
        - **CentOS/AlmaLinux:** Free clones of RHEL.
        - **Fedora:** Community-driven with cutting-edge features.
    - Commands:
        - `rpm -qa`: Query installed packages.
        - `yum` or `dnf`: Advanced package management.
- **Debian-Based:**
    - Uses `dpkg` for package management.
    - Examples:
        - **Debian:** Stability-focused.
        - **Ubuntu:** User-friendly and widely used.
    - Commands:
        - `dpkg -l`: List installed packages.
        - `apt`: High-level package management tool.

### **5. Graphical User Interface (GUI)**

The GUI system in Linux enhances user interaction through graphical elements.

- **Display Managers:**
    - Handle user logins and desktop session management.
    - Examples: GDM (GNOME), LightDM, SDDM (KDE).
- **Window Managers:**
    - Control window appearance and behavior.
    - Examples: GNOME Shell (full desktop), i3 (tiling manager), Openbox (minimalist).
- **X Server:**
    - The traditional display server for rendering graphics.
    - Tool: `xrandr` for managing displays.
- **Wayland:**
    - Modern replacement for X Server.
    - Focuses on security and performance.
    - Adoption: GNOME, KDE.

### **6. Software Licensing**

Linux is built on diverse licensing models, defining how software can be used and distributed.

- **Open Source Software:**
    - Source code is publicly available.
    - Allows modification and redistribution.
    - Examples: Apache, Linux kernel.
- **Free Software:**
    - Emphasizes user freedom (to run, modify, share).
    - Governed by organizations like the Free Software Foundation.
    - Examples: GNU utilities.
- **Proprietary Software:**
    - Closed-source with restricted use.
    - Examples: Some device drivers, commercial software.
- **Copyleft:**
    - Requires derivative works to use the same license as the original.
    - Example: GNU General Public License (GPL).

1.2 Summarize Linux device management concepts and tools.

### Linux Device Management Concepts and Tools

### **1. Kernel Modules**

Kernel modules are dynamically loadable pieces of code that extend the functionality of the Linux kernel. They are used to add support for hardware devices, file systems, and other features without rebuilding the kernel.

- **Tools for Managing Kernel Modules:**
    - **`depmod`:** Generates a list of module dependencies for the system.
    - **`insmod`:** Inserts a module into the kernel manually.
    - **`lsmod`:** Lists all currently loaded modules.
    - **`modinfo`:** Displays information about a specific module (e.g., dependencies, version).
    - **`modprobe`:** Loads or removes modules along with their dependencies.
    - **`rmmod`:** Removes a module from the kernel.

---

### **2. Device Management**

Device management involves monitoring, configuring, and troubleshooting hardware devices.

- **Tools for Device Management:**
    - **`dmesg`:** Displays kernel ring buffer messages, often used to check hardware and driver issues.
    - **`dmidecode`:** Retrieves information about the system's hardware (e.g., BIOS, CPU, memory).
    - **`ipmitool`:** Interface for managing and monitoring hardware using IPMI (Intelligent Platform Management Interface).
    - **`lm_sensors`:** Monitors hardware sensors (e.g., temperature, voltage, fan speed).
    - **`lscpu`:** Displays detailed CPU architecture information.
    - **`lshw`:** Lists detailed information about the system's hardware.
    - **`lsmem`:** Displays information about the system's memory.
    - **`lspci`:** Lists PCI devices connected to the system.
    - **`lsusb`:** Lists USB devices connected to the system.

---

### **3. Initrd Management**

The initial RAM disk (`initrd`) is used during the Linux boot process to load necessary drivers and prepare the real root filesystem.

- **Tools for Managing `initrd`:**
    - **`dracut`:** Utility for generating `initrd` images with modular components.
    - **`mkinitrd`:** Legacy tool for creating `initrd` images.

---

### **4. Custom Hardware**

Linux supports custom hardware, including embedded systems and GPUs.

- **Examples:**
    - **Embedded Systems:** Tailored for specific devices with minimal hardware resources.
    - **Graphics Processing Unit (GPU) Use Cases:** Often used in high-performance computing, machine learning, and gaming.
    - **`nvtop`:** A command-line utility for monitoring GPU usage and performance, especially for NVIDIA GPUs.



1.3 Given a scenario, manage storage in a Linux System
### **1. Logical Volume Manager (LVM)**

### **Logical Volume**

- Flexible storage management tool for resizing, creating, and managing volumes.
- **Commands:**
    - `lvchange`: Change attributes of a logical volume.
    - `lvcreate`: Create a logical volume.
    - `lvdisplay`: Display details of logical volumes.
    - `lvremove`: Remove a logical volume.
    - `lvresize/lvextend`: Resize or extend a logical volume.
    - `lvs`: Summarize logical volumes.

### **Volume Group**

- Aggregates physical volumes to provide storage for logical volumes.
- **Commands:**
    - `vgcreate`: Create a volume group.
    - `vgdisplay`: Display volume group details.
    - `vgextend`: Add physical volumes to a volume group.
    - `vgexport/vgimport`: Export/import a volume group for use on another system.
    - `vgremove`: Remove a volume group.
    - `vgs`: Summarize volume groups.
    - `vgscan`: Scan for volume groups.

### **Physical Volume**

- Represents the physical storage medium used in LVM.
- **Commands:**
    - `pvcreate`: Create a physical volume.
    - `pvdisplay`: Display details of physical volumes.
    - `pvremove`: Remove a physical volume.
    - `pvresize`: Resize a physical volume.
    - `pvs`: Summarize physical volumes.
    - `pvscan`: Scan for physical volumes.

---

### **2. Partitions**

- Dividing physical storage into logical sections for better management.
- **Commands:**
    - `blkid`: Display block device attributes.
    - `fdisk/gdisk`: Partition a disk.
    - `growpart`: Expand a partition.
    - `lsblk`: List block devices.
    - `parted`: Create and manage partitions.

---

### **3. Filesystems**

### **Formats**

- Common Linux filesystems:
    - `xfs`: High-performance journaling filesystem.
    - `ext4`: Standard filesystem with extended journaling and performance.
    - `btrfs`: Advanced filesystem with features like snapshots and compression.
    - `tmpfs`: Temporary in-memory filesystem.

### **Utilities**

- Commands for managing and troubleshooting filesystems:
    - `df`: Check disk space usage.
    - `du`: Check directory/file space usage.
    - `fio`: Benchmark I/O performance.
    - `fsck`: Check and repair a filesystem.
    - `mkfs`: Create a new filesystem.
    - `resize2fs`: Resize ext2/3/4 filesystems.
    - `xfs_growfs`: Grow an XFS filesystem.
    - `xfs_repair`: Repair an XFS filesystem.

---

### **4. Redundant Array of Independent Disks (RAID)**

- Combines multiple disks for redundancy or performance.
- **Commands/Tools:**
    - `/proc/mdstat`: Monitor RAID arrays.
    - `mdadm`: Manage and create RAID arrays.

---

### **5. Mounted Storage**

### **Mounting**

- Mount storage devices for use.
- Files:
    - `/etc/fstab`: Persistent mount configuration.
    - `/etc/mtab`: Active mounted filesystems.
    - `/proc/mounts`: Mounted filesystem details.
- **Commands:**
    - `autofs`: Automounting file systems on demand.
    - `mount`: Mount a filesystem.
    - `umount`: Unmount a filesystem.

### **Mount Options**

- Options to control how filesystems are mounted:
    - `noatime`: Do not update file access times.
    - `nodev`: Do not allow device files.
    - `nodiratime`: Do not update directory access times.
    - `noexec`: Prevent execution of binaries.
    - `nofail`: Do not fail if the device is not available.
    - `nosuid`: Ignore set-user-ID and set-group-ID bits.
    - `remount`: Remount an already mounted filesystem.
    - `ro`: Mount read-only.
    - `rw`: Mount read-write.

### **Network Mounts**

- Mount shared storage over the network.
    - **Network File System (NFS):** For mounting remote directories.
    - **Server Message Block (SMB)/Samba:** For mounting Windows shares.

---

### **6. Inodes**

- Data structures containing metadata about files.
- Limited by the filesystem and can cause issues if exhausted
1.4 Given a scenario, manage network services and configurations on a Linux server.
  1. Network Configuration
a) /etc/hosts
Defines hostname-to-IP mappings.
Example: Add a custom hostname:
echo "192.168.1.10 myserver.local" >> /etc/hosts
​
b) /etc/resolv.conf
Configures DNS servers.
Example: Add a DNS server:
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
​
c) /etc/nsswitch.conf
Determines the order of name resolution.
Example: Edit for DNS preference:
hosts: files dns
​
2. NetworkManager
a) nmcli
A command-line tool to manage network connections.
List connections:
nmcli connection show
​
Connect to a Wi-Fi network:
nmcli device wifi connect "SSID" password "password"
​
b) nmconnect
Simplifies connecting to Wi-Fi or VPN (useful for scripts).
Example:
nmconnect "SSID" password "password"
​
3. Netplan
a) netplan apply
Applies network configuration changes.
Example:
sudo netplan apply
b) netplan status
Shows the current status of network configurations.
Example:
netplan status
​
c) netplan try
Tests a new configuration before applying it permanently.
Example:
sudo netplan try
​
d) Configuration Files
Located in /etc/netplan/.
Example Configuration:
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: true
​
4. Common Network Tools
a) arp
Displays the ARP table.
Example:
arp -a
​
b) curl
Transfers data from URLs.
Example:
curl http://example.com
​
c) dig
Performs DNS lookups.
Example:
dig example.com
​
d) ethtool
Displays or changes Ethernet device settings.
Example:
ethtool eth0
### **e) `hostname`**

Displays or sets the system hostname.

**Example:**

```bash
hostnamectl set-hostname new-hostname
```

### **f) `ip`**

A versatile tool for network management.

- **Show IP addresses:**
    
    ```bash
    ip address
    ```
    
- **Show network interfaces:**
    
    ```bash
    ip link
    ```
    
- **Show routes:**
    
    ```bash
    ip route
    ```
    

### **g) `iperf3`**

Tests network bandwidth.

**Example:**

On the server:

```bash
iperf3 -s
```

On the client:

```bash
iperf3 -c server_ip
```

### **h) `mtr`**

Combines traceroute and ping for network diagnostics.

**Example:**

```bash
mtr example.com
```

### **i) `nc` (Netcat)**

Reads/writes over network connections.

**Example:**

```bash
nc -zv example.com 80
```

- Tests if port 80 is open on `example.com`.

### **j) `nmap`**

Scans networks for open ports and services.

**Example:**

```bash
nmap example.com
```

### **k) `nslookup`**
Performs DNS lookups.
Example:
nslookup example.com
​
l) ping/ping6
Sends ICMP packets to test connectivity.
Example:
ping example.com
​
m) ssh
Connects to a remote server via SSH.
Example:
ssh user@remote_server
​
n) tcpdump
Captures network packets for analysis.
Example:
tcpdump -i eth0
​
o) tracepath
Traces the route to a destination.
Example:
tracepath example.com
​
p) traceroute
Traces the route to a destination (more detailed than tracepath).
Example:
traceroute example.com


1.5 Given a scenario, manage a Linux system using common shell operations
### **1. Common Environmental Variables**

Environmental variables store configuration details for the shell and system. Common ones include:

- **DISPLAY:** Defines the display server for GUI applications.
- **HOME:** The path to the user's home directory (e.g., `/home/username`).
- **PATH:** A list of directories where the shell looks for executable commands.
- **PS1:** Defines the appearance of the shell prompt.
- **SHELL:** The user's default shell (e.g., `/bin/bash`).
- **USER:** The current logged-in username.

---

### **2. Paths**

Paths specify the location of files and directories:

- **Absolute Paths:** Start from the root directory (`/`) and provide the full path to a file (e.g., `/etc/passwd`).
- **Relative Paths:** Refer to locations relative to the current directory.
    - **.** (Single dot): Represents the current directory.
    - **..** (Double dot): Represents the parent directory.
    - **~** (Tilde): Represents the home directory of the current user.

---

### **3. Shell Environment Configurations**

Configuration files customize the shell environment:

- **.bashrc:** Contains user-specific shell preferences and aliases, loaded in interactive non-login shells.
- **.bash_profile:** Loaded for login shells, used for setting environment variables.
- **.profile:** A generic configuration file for login shells, often used with non-Bash shells.

---

### **4. Channel Redirection**

Shell redirection manipulates input and output streams:

- **<**: Redirects input from a file.
- **>**: Redirects output to a file (overwriting).
- **>>**: Appends output to a file.
- **<< (Here Docs):** Redirects a block of input directly into a command.
- **Standard Output (stdout):** Default output stream (descriptor 1).
- **Standard Error (stderr):** Default error stream (descriptor 2).
- **Standard Input (stdin):** Default input stream (descriptor 0).
- ### **5. Basic Shell Utilities**

Common commands for managing text, files, and processes:

- **! and !!**: Rerun previous commands (`!` for a specific command, `!!` for the last command).
- **alias:** Create shortcuts for commands.
- **awk:** Process and manipulate text files.
- **bc:** A command-line calculator.
- **cat:** Concatenate and display file contents.
- **cut:** Extract sections of text from files.
- **echo:** Print text to stdout.
- **grep:** Search for text patterns in files.
- **head and tail:** Display the first or last lines of a file.
- **history:** Display command history.
- **less and more:** View text files one screen at a time.
- **printf:** Format and print output.
- **sed:** Stream editor for text manipulation.
- **sort:** Sort lines of text.
- **source:** Execute a script in the current shell.
- **tee:** Redirect output to a file and stdout simultaneously.
- **tr:** Translate or delete characters.
- **uname:** Display system information.
- **uniq:** Remove duplicate lines.
- **wc:** Count lines, words, and characters in a file.
- **xargs:** Build and execute command lines from input.

---

### **6. Text Editors**

Editors for creating and modifying files:

- **vi/vim:** Powerful text editor for advanced users.
- **nano:** Simple and user-friendly text editor.
1.6 Given a scenario, perform backup and restore operations for a Linux server.
  1. Archiving Tools
a) cpio
Used for creating or extracting archive files.
Examples:
Create an archive from a list of files:
ls | cpio -ov > archive.cpio
​
Extract an archive:
cpio -idv < archive.cpio
​
Copy files from one directory to another:
find . -type f | cpio -pdm /destination/directory
b) tar
A widely used archiving tool for creating .tar files.
Examples:
Create a tar archive:
tar -cvf archive.tar file1 file2
​
Extract a tar archive:
bash
Copy code
tar -xvf archive.tar
​
Create and compress with gzip:
tar -czvf archive.tar.gz file1 file2
​
Extract a gzip-compressed tar archive:
tar -xzvf archive.tar.gz
​
List the contents of a tar archive:
tar -tvf archive.tar
2. Compression Tools
a) 7-Zip
A high-compression ratio tool.
Examples:
Compress a file:
7z a archive.7z file1
​
Extract a .7z file:
7z x archive.7z
​
List contents of a .7z archive:
7z l archive.7z
b) bzip2
Compresses files with .bz2 format.
Examples:
Compress a file:
bzip2 file.txt
​
Decompress a .bz2 file:
bunzip2 file.txt.bz2
c) gzip
Compresses files with .gz format.
Examples:
Compress a file:
gzip file.txt
​
Decompress a .gz file:
gunzip file.txt.g
d) unzip
Used to extract .zip files.
Examples:
Extract a .zip file:
unzip archive.zip
​
List the contents of a .zip file:
unzip -l archive.zip
e) xz
Compresses files with .xz format.
Examples:
Compress a file:
xz file.txt
​
Decompress an .xz file:
unxz file.txt.xz
3. Other Tools
a) dd
Used for low-level copying and disk imaging.
Examples:
Create a disk image:
dd if=/dev/sdX of=disk.img bs=1M
​
Restore a disk image:
dd if=disk.img of=/dev/sdX bs=1M
​
Wipe a disk with random data:
dd if=/dev/urandom of=/dev/sdX bs=1M
b) ddrescue
Used to recover data from damaged disks.
Examples:
Clone a failing disk:
ddrescue /dev/sdX disk.img logfile


​
Resume a previously interrupted rescue:
ddrescue -r 3 /dev/sdX disk.img logfile
c) rsync
Used for fast and efficient file or directory synchronization.
Examples:
Synchronize a local directory:
rsync -av /source/directory /destination/directory


​
Sync files to a remote server:
rsync -av file.txt user@remote:/path/to/destination


​
Show progress while syncing:
rsync -av --progress file.txt /destination
d) zcat
Reads compressed .gz files without extracting them.
Examples:
Display the contents of a compressed file:
zcat file.txt.gz


​
e) zgrep
Searches inside .gz compressed files.
Examples:
Search for a term in a .gz file:
zgrep "pattern" file.txt.gz


​
f) zless
Displays the contents of a .gz file with pagination.
Examples:
View a compressed file page-by-page:
zless file.txt.gz




1.7 Summarize virtualization on Linux systems.
1. Linux Hypervisors
A hypervisor is software or firmware that allows you to run virtual machines (VMs) on a physical host.
a) Quick Emulator (QEMU)
A generic and open-source machine emulator and virtualizer.
Can emulate hardware entirely, making it platform-independent.
Works well with KVM to improve performance through hardware acceleration.
Example:
Start a virtual machine using QEMU:
qemu-system-x86_64 -enable-kvm -m 2048 -hda disk.img


​
b) Kernel-based Virtual Machine (KVM)
A Linux kernel module that enables hardware virtualization.
Turns the Linux kernel into a hypervisor.
Used in conjunction with tools like QEMU for full virtualization.
Command to check KVM support:
lsmod | grep kvm
2. Virtual Machines (VMs)
a) Paravirtualized Drivers
Enhance VM performance by enabling the guest OS to interact more efficiently with the host.
VirtIO is a standard for paravirtualized drivers, improving performance for devices like network and disk.
b) Disk Image Operations
Convert: Change disk formats using qemu-img.Example:
qemu-img convert -f raw -O qcow2 disk.img disk.qcow2


​
Resize: Increase or decrease the size of a disk image.Example:
qemu-img resize disk.qcow2 +10G


​
Image Properties: Check or modify attributes of disk images.Example:
qemu-img info disk.qcow2


​
c) VM States
VMs can be in various states: running, paused, stopped, or saved.
Example (pause a VM with virsh):
virsh suspend vm_name
d) Nested Virtualization
Running a hypervisor inside another VM.
Requires hardware support (e.g., Intel VT-x or AMD-V).
Example (enable nested virtualization):
echo "options kvm-intel nested=1" > /etc/modprobe.d/kvm-intel.conf
3. VM Operations
a) Resources
Storage: Allocate virtual disks to a VM.
RAM: Define memory for the VM during creation.Example:
qemu-system-x86_64 -m 4096 -hda disk.img


​
CPU: Assign specific CPU cores to a VM.
b) Baseline Image Templates
Create base VM images to speed up deployment.
Example: Clone a base image to create a new VM:
qemu-img create -f qcow2 -b base.qcow2 new_vm.qcow2

c) Cloning
Duplicate an existing VM or its disk.
Example:
virt-clone --original vm_name --name new_vm_name --file /path/to/new_disk.img


​
d) Migrations
Move a VM between hosts without stopping it (live migration).
Example:
virsh migrate --live vm_name qemu+ssh://destination_host/system


​
e) Snapshots
Save the state of a VM at a specific point in time.
Example:
virsh snapshot-create-as vm_name snapshot_name

### **4. Bare Metal vs. Virtual Machines**

| Feature | Bare Metal | Virtual Machines |
| --- | --- | --- |
| Performance | Direct hardware access (faster). | Slight overhead due to virtualization. |
| Flexibility | Limited to OS installed on hardware. | Multiple OS instances on a single host. |
| Cost | Higher (dedicated hardware). | Lower (multiple VMs share resources). |
### **5. Network Types**

Different ways VMs communicate with the host and external networks:

### **a) Bridged**

- VMs share the host's physical network interface.
- Appears as if VMs are directly connected to the external network.
- **Example (via `virsh`):**
    
    ```bash
    virsh attach-interface vm_name --type bridge --source br0 --model virtio
    
    ```
    

### **b) Network Address Translation (NAT)**

- VMs access the external network through the host's IP address.
- Default networking mode in many setups.

### **c) Host-Only/Isolated**

- VMs communicate only with the host and other VMs, not the external network.

### **d) Routed**

- VMs are on a separate network and can communicate with the external network via routing.

### **e) Open**

- A completely unrestricted network, typically used for specific testing scenarios.

- ### **6. Virtual Machine Tools**

### **a) `libvirt`**

- A toolkit for managing virtualization platforms like KVM and QEMU.
- Provides APIs and a daemon (`libvirtd`) for managing VMs.

### **b) `virsh`**

- Command-line tool for managing VMs via `libvirt`.**Examples:**
1. Start a VM:
    
    ```bash
    virsh start vm_name
    
    ```
    
2. List all VMs:
    
    ```bash
    virsh list --all
    
    ```
    

### **c) `virt-manager`**

- A GUI-based tool to manage VMs.
- Provides an easy-to-use interface for creating, configuring, and managing virtual machines.
