# Docker Swarm Cluster com Vagrant

## Descrição
Este projeto cria um cluster Docker Swarm local utilizando Vagrant, com 1 nó master e 3 nós workers.

### Passos para execução

1. Clone este repositório.
2. Navegue até a pasta do projeto.
3. Execute o comando `vagrant up` para criar as VMs.
4. Após as VMs serem criadas, conecte-se ao nó master:
   ```bash
   vagrant ssh master
   ```
5. Inicialize o Docker Swarm no nó master:
   ```bash
   docker swarm init --advertise-addr 192.168.50.10
   ```
6. Siga as instruções para adicionar os nós worker ao Swarm.

### Requisitos
- VirtualBox
- Vagrant
- Docker
