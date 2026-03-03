*This activity has been created as part of the 42 curriculum by mjabarin.*

# 🐧 Born2beRoot

---

## 📖 Description

Born2beRoot is a system administration project focused on installing and configuring a secure Linux server inside a virtual machine.

The goal of this activity is to understand the fundamentals of Linux system administration, server hardening, user management, and basic security practices. The entire setup is performed without a graphical interface, reinforcing command-line proficiency and system-level understanding.

By the end of the project, the system must be properly secured, configured according to strict rules, and monitored using a custom Bash script that displays some information to users every 10 mins.

---

## 🛠 Project Description & Design Choices

### 🔹 Chosen Operating System: Debian

I chose **Debian** for this project due to its stability, large community support, and simplicity for beginners in system administration.

#### ✅ Debian – Pros
- Stable and reliable
- Large package repository
- Extensive documentation
- Simpler default configuration

#### ❌ Debian – Cons
- Slower release cycle
- Older package versions compared to rolling distributions

---

### 🔄 Debian vs Rocky Linux

| Debian | Rocky Linux |
|---------|------------|
| Community-driven | Enterprise-focused (RHEL compatible) |
| Uses APT package manager | Uses DNF/YUM package manager |
| AppArmor by default | SELinux by default |
| Simpler learning curve | Closer to enterprise server environments |

**Conclusion:** Debian is more beginner-friendly, while Rocky Linux better reflects enterprise environments.

---

### 🔐 AppArmor vs SELinux

| AppArmor | SELinux |
|-----------|----------|
| Easier to configure | More powerful and granular |
| Profile-based | Label-based |
| Less complex | More complex but more secure |

AppArmor was chosen because it integrates smoothly with Debian and is easier to manage for this project scope.

---

### 🔥 UFW vs firewalld

| UFW | firewalld |
|------|-----------|
| Simple interface | More advanced and dynamic |
| Ideal for small setups | Suitable for enterprise networks |
| Uses iptables backend | Uses nftables/iptables backend |

UFW was selected due to its simplicity and quick configuration.

---

### 💻 VirtualBox vs UTM

| VirtualBox | UTM |
|-------------|-----|
| Cross-platform | Optimized for macOS (Apple Silicon) |
| Mature and widely used | Lightweight alternative |
| More configuration options | Simpler interface |

VirtualBox was chosen because of its flexibility and compatibility across operating systems.

---

### 🧩 Main Design Choices

- **Partitioning:** Manual partitioning with LVM for flexible disk management.
- **Security Policies:** Strict password expiration rules, strong password enforcement, and limited sudo access.
- **User Management:** Custom user and group creation with proper privilege separation.
- **Services Installed:** SSH (custom port), UFW firewall, sudo configuration, monitoring Bash script.
- **Monitoring:** Automated script displaying system stats every 10 minutes.

---

## 🚀 Instructions

### 1️⃣ Installation

1. Download Debian ISO from the official website.
2. Create a virtual machine using VirtualBox.
3. Perform manual partitioning with LVM.
4. Install SSH server during setup (or manually after installation).
5. Disable root SSH login.
6. Configure UFW to allow only required ports.

### 2️⃣ Configuration

- Create a user with sudo privileges.
- Implement password policy:
  - Expiration days
  - Minimum days before change
  - Complexity requirements
- Configure sudo rules.
- Install and configure monitoring script.
- Set SSH to use a custom port.

### 3️⃣ Execution

To run the monitoring script manually:

```bash
bash monitoring.sh
