# CKAD 

### Minikube setup (Arch Linux)
```bash
sudo pacman -S minikube
sudo usermod -aG libvirt $(whoami)
sudo systemctl enable libvirtd.service
minikube config set driver kvm2

minikube start -n 3
minikube kubectl -- get pods -A

minikube delete
```

### Exam Setup 

- Bash completion

```bash
# set up autocomplete in bash into the current shell, bash-completion package should be installed first.
source <(kubectl completion bash) 

# add autocomplete permanently to your bash shell.
echo "source <(kubectl completion bash)" >> ~/.bashrc 
```

- kubectl alias

```bash
alias k=kubectl
complete -o default -F __start_kubectl k
```

- kubectl exports

```bash
export do="--dry-run=client -o yaml"
```

- `~/.vimrc`
```bash
set et ts=2
```