# Definições de endereços IPs da Rede e Nomes de Hosts:

```
------------------------------------------------------------------------------------------------------------
|  DESCRICAO  |  IP                  |   hostname        |          FQDN                |     aliase       |
------------------------------------------------------------------------------------------------------------
| VM1-PC1     | 192.168.23.33        |   srv-vm1-pc1     | lucas1.grupo3.ifalara.net    |       vpn        |
| VM2-PC1     | 192.168.23.34        |   srv-vm2-pc1     | lucas2.grupo3.ifalara.net    |       mail       |
| VM1-PC2     | 192.168.23.35        |   srv-vm1-pc2     | bia1.grupo3.ifalara.net      |       www        |
| VM2-PC2     | 192.168.23.36        |   srv-vm2-pc2     | bia2.grupo3.ifalara.net      |       file       |
| VM1-PC3     | 192.168.23.37        |   srv-vm1-pc3     | jesse1.grupo3.ifalara.net    |       angular    |
| VM2-PC3     | 192.168.23.38        |   srv-vm2-pc3     | jesse2.grupo3.ifalara.net    |       vue        |
| VM1-PC4     | 192.168.23.39        |   srv-vm1-pc4     | roberta1.grupo3.ifalara.net  |       react      |
| VM2-PC4     | 192.168.23.40        |   srv-vm2-pc4     | roberta2.grupo3.ifalara.net  |       mongo      |
------------------------------------------------------------------------------------------------------------
```

# Modelo de rede P2P criada
![Diagrama](https://user-images.githubusercontent.com/64742095/186517877-003ba695-8954-48cb-a868-3ba522790809.png)

## Topologia Física 
### Barramento
Computadores ligados de forma linear. O final do barramento é onde se localiza o terminal responsável por controlar o fluxo de dados da rede.

## Requisitos de Hardware
### Hardware utilizado nas VM's
* Núcleos lógico de processamento: 1
* RAM: 2048MB
* Espaço em disco: 10GB dinamicamente alocados

## Configurando os ambientes

### Executar o comando 
```
sudo hostnamectl set-hostname srv-vm1-pc1
```
para definir o nome da máquina

## Instalando o SSH
```
systemctl status ssh
sudo apt-get install openssh-server
systemctl status ssh
```

## Verificando se a conexão tcp nas portas 22 está como LISTENING
```
netstat -an | grep LISTEN
```
## Configuração do Firewall
Permitindo conexões remotas via SSH
```
sudo ufw status
sudo ufw allow ssh
sudo ufw status
```
Ativando o Firewall
```
sudo ufw enable
```

## Configurando a interface de rede
# {Aqui vai ter uma imagem da configuração da rede}

## Acessando a VM remotamente

```
ssh <usuário>@<ipDoServidorRemoto>
```
Exemplo

```
ssh administrador@192.168.56.101 #endereço da VM1 do PC3
```

## Configurando rede de hospedeiros para a cominucação entre o Host

<img src="/images/criandoAdapt.png">

## Configurando o servidor DHCP no adaptador

<img src="/images/configAdapt2.png">

## Adicionando o adaptador Host-Only em uma VM

## Ativando o dhcp4 para o adaptador 2
# {imagem}

## Verificando as interfaces

```
ifconfig -a
```
# {image}

## Acessando a VM remotamente

no terminal do computador
```
ssh administrador@192.168.56.101
```

# Testes/Validações
