## Requisitado pelo professor: Alaelson Jatobá <br /> Disciplina: Infraestrutura de Redes <br /> Data: 01/09/2020 <br /> Turma: 923 <br /> Grupo: 3

### Integrantes
* Nome: Jessé Diego da Silva Oliveira
* Nome: Lucas Rosendo de Farias
* Nome: Maria Beatriz Ferreira dos Santos
* Nome: Maria Roberta de Lima Santos


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

### Baixando o arquivo .ova da máquina virtual com o sistema operacional 

```
scp aluno@192.168.101.10:~/Public/iso-images/ubuntu-server-mini.ova
```

### Antes de iniciar a máquina virtual, baixe o Extension Pack
```
sudo apt install virtualbox-ext-pack
```

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

<img src="/images/configRedeBridge.png">

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

<img src="/images/config2Adapt.png">

## Adicionando o adaptador Host-Only em uma VM

## Ativando o dhcp4 para o adaptador 2
<img src="/images/configAdapt.png">

## Verificando as interfaces

```
ifconfig -a
```
<img src="/images/ifconfig.png">

## Acessando a VM remotamente

no terminal do computador
```
ssh administrador@192.168.56.101
```

# Testes/Validações

## Ping para 192.168.23.35, www e srv-vm1-pc2

![image](https://user-images.githubusercontent.com/64742095/187786254-4d5ebca6-dd72-461e-a079-15652c8b1798.png)
![image](https://user-images.githubusercontent.com/64742095/187786514-b127706d-e87d-4ec1-b9cd-b867d353673f.png)
![image](https://user-images.githubusercontent.com/64742095/187786690-bc3c5d97-585e-4d1a-b961-10366e93d8c4.png)

## Acessando remotamente a VM2 do PC 2

![image](https://user-images.githubusercontent.com/64742095/187787624-16783ef0-55ad-4a57-83af-4b46bc2aaacd.png)

## Ping para 192.168.23.38, vue e srv-vm2-pc3

![image](https://user-images.githubusercontent.com/64742095/187788448-f032ce79-40cb-4803-8ed9-1d9991625b91.png)
![image](https://user-images.githubusercontent.com/64742095/187788571-00e3c118-74ba-4716-8da6-a752fadfb5b8.png)
![image](https://user-images.githubusercontent.com/64742095/187788722-1197ec65-4a27-4f44-a92a-bdeb8ca45cf2.png)

## Acessando remotamente a VM1 do PC 3

![image](https://user-images.githubusercontent.com/64742095/187793287-85bfea8f-6b7f-43b5-bd8b-66323ed7174e.png)

## Ping para 192.168.23.37, angular e srv-vm1-pc3

![image](https://user-images.githubusercontent.com/64742095/187793475-6becf570-0e19-448d-b384-8f1418ec11a5.png)
![image](https://user-images.githubusercontent.com/64742095/187793638-27d11660-c3b7-4ba4-9212-3a0909b7ab67.png)
![image](https://user-images.githubusercontent.com/64742095/187793715-28a2dd39-36fc-4e1e-a6d6-fd0b9cf01ca8.png)
 
 ## Acessando remotamente a VM1 do PC 3
 
 ![image](https://user-images.githubusercontent.com/64742095/187794293-60caeff7-d414-4a8c-826f-b3b0c488f58d.png)


## Objetivos do projeto:
* Colocar em prática o que aprendemos em aula
* Criar um tutorial resumido ensinando a fazer a conexão entre VM's de PC's diferentes 
* Testar os conhecimentos adquiridos em aulas
