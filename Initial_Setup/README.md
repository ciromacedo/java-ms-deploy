# Initial_Setup

Passo a passo de configuração e deploy dos microsserviços em uma VM DigitalOcean. Contém todo processo de configuração incluindo instalação do Docker.
Requisitos:
- Ubuntu 24.10 x64
- Regular SSD
- 2 GB ($12/mo)

Após criar a VM, acessar via SSH e executar o passo a passo descrito a seguir:

### Atualize os pacotes existentes
```
sudo apt update && sudo apt upgrade -y
```

### Instalar Ansible + Git + Dependências
```
sudo apt install ansible -y && sudo apt install ansible -y && sudo apt update && apt install python3-docker -y
```

### Instalar Collections extras para o Ansible
```
ansible-galaxy collection install community.docker
```

### Clonar o repositório de instalação
```
git clone https://github.com/ciromacedo/java-ms-deploy.git
```

### Executar o playbook de implantação
```
cd java-ms-deploy/Initial_Setup && ansible-playbook -K initial_setup.yml
```