# 🚀 Install Docker on macOS Using Colima (Without Docker Desktop)

This guide will set up **Docker** with **Colima** (a lightweight VM) and **LazyDocker** (a terminal UI for Docker) on macOS, without requiring Docker Desktop.

## 📌 Prerequisites
- macOS (Intel or Apple Silicon)
- Homebrew installed

If you don’t have Homebrew, install it:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

## 1️⃣ Install Colima and Docker CLI
Run the following command to install **Colima**, **Docker CLI**, and **other required tools**:
```bash
brew install colima docker docker-compose
```

---

## 2️⃣ Start Colima VM
Start **Colima VM** with Docker support:
```bash
colima start
```

For a more powerful VM (e.g., 4 CPU cores, 6GB RAM, GPU support):
```bash
colima start --cpu 4 --memory 6 --gpu
```

---

## 3️⃣ Verify Docker is Running
Check that Docker is installed and working:
```bash
docker version
```

Test Docker by running:
```bash
docker run hello-world
```
If successful, you’ll see a message saying **"Hello from Docker!"**

---

## 4️⃣ Configure Docker to Auto-Start with Colima
To make Colima start automatically when you log in, add this to your shell config (`~/.zshrc` or `~/.bashrc`):
```bash
echo 'alias docker="colima start && docker"' >> ~/.zshrc
source ~/.zshrc
```
Now, Docker will start automatically when you run any `docker` command.

---

## 5️⃣ (Optional) Enable Kubernetes in Colima
If you need Kubernetes, start Colima with Kubernetes support:
```bash
colima start --kubernetes
```
Verify Kubernetes is running:
```bash
kubectl get nodes
```

---

# 🛠 Install LazyDocker (TUI for Docker)
LazyDocker is a terminal UI for managing Docker containers, images, volumes, and networks.

### 1️⃣ Install LazyDocker
```bash
brew install lazydocker
```

### 2️⃣ Run LazyDocker
```bash
lazydocker
```

### 3️⃣ (Optional) Create an Alias
Add this alias to `~/.zshrc` (or `~/.bashrc`) for quicker access:
```bash
echo 'alias ld="lazydocker"' >> ~/.zshrc
source ~/.zshrc
```
Now you can start LazyDocker with:
```bash
ld
```

---

## 🎯 Summary
✅ Installed **Docker CLI** & **Colima**  
✅ Started a lightweight VM for Docker  
✅ Verified Docker is running  
✅ Installed **LazyDocker** for easy management  
✅ (Optional) Enabled Kubernetes

Now you have **Docker running on macOS without Docker Desktop**! 🎉

