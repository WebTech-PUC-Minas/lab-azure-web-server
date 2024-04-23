# Laboratório de Criação de Servidor Web no Microsoft Azure

Criação de uma máquina virtual no Microsoft Azure para rodar um servidor web

## Tecnologias utilizadas

<div style="display: flex; gap: 10px;">
    <img width="50px" src="Icones/Microsoft_Azure.png" alt="Microsoft Azure">
    <img width="50px" src="Icones/4375122_logo_ubuntu_icon.png" alt="Ubuntu">
    <img height="50px" width="100px" src="Icones/httpd.png" alt="Apache HTTP Server">
</div>

## Onde aplicar

Este projeto pode ser aplicado quando precisamos de um servidor web.

## Roadmap

### STEP 1 - Criação da conta de estudante no Microsoft Azure

O Instituto de Ciências Exatas e Informática (ICEI) da PUC Minas possuí parceria com a Microsoft, dando um crédito de US$100 para cada aluno anualmente. Para criar sua conta de estudante, basta seguir o [tutorial no site do ICEI](https://icei.pucminas.br/index.php/azurepucminas).

### STEP 2 - Criação de uma máquina virtual na Azure

No [console do Microsoft Azure](https://portal.azure.com/), em Azure services, clique em "Virtual machines" (Máquinas Virtuais).

Caso não apareça a opção "Virtual machines", na barra de pesquisa ("Search resources, services, and docs (G+/)"), digite "Virtual machines", e clique na primeira opção.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/Screenshot 2024-04-23 at 13-11-41 Microsoft Azure.png" alt="Tela inicial do Microsoft Azure. No topo dela aparece 'Azure Services'."></div>
    <div><span>Tela inicial do Micrsoft Azure</span></div>
</div>
</p>

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/Screenshot 2024-04-23 at 13-15-30 Microsoft Azure.png" alt="Opções do 'Azure services': 'Virtual machines', 'Education', 'Monitor', 'Storage accounts', 'Subscriptions', 'All resources', 'Quickstart Center', 'App Services', 'More services'."></div>
    <div><span>Opções do Azure services</span></div>
</div>
</p>

No menu "Virtual machines" (Máquinas Virtuais), clique no botão "Create", e depois em "Azure virtual machine".

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/Screenshot 2024-04-23 at 13-11-49 Microsoft Azure.png" alt="Menu 'Virtual machines'. Barra superior com os botões: 'Create', 'Switch to classic', 'Reservations', 'Manage view', 'Refresh', 'Export to CSV', 'Open query', 'Assign tags', 'Start', 'Restart', 'Stop', 'Delete', 'Services', 'Maintenance'."></div>
    <div><span>Menu 'Virtual machines'</span></div>
</div>
</p>

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/Screenshot 2024-04-23 at 13-42-05 Microsoft Azure.png" alt="Opções de 'Create' em 'Virtual machine': 'Azure virtual machine', 'Azure virtual machine with preset configuration', 'More VMs and related solutions'."></div>
    <div><span>Opções de 'Create' em 'Virtual machine'</span></div>
</div>
</p>

No menu "Create a virtual machine" (criar uma máquina virtual):

**Instance details (Detalhes de instância)**:

- Em  "Virtual machine name" (nome da máquina virtual), digite: ```Web-Server```.

- Em "Region" (Região), selecione ```(US) East US``` (Leste dos EUA).

- Em "Availability options" (Opções de disponibilidade), selecione ```No infrastructure redundancy required``` (Nenhuma redundância de infraestrutura necessária).

- Em "Image" (Imagem), selecione ```Ubuntu Server 20.04 LTS - x64 Gen2```.

- Em "Size" (Tamanho), selecione ```Standard_B1ls - 1 vcpu, 0.5 GiB memory (US$ ????/month)```

**Administrator account (Conta de administrador)**:

- Em "Authentication type" (Tipo de autenticação), selecione ```SSH public key``` (chave pública SSH).

- Em "Username" (Nome de usuário), digite ```azureuser```.

- Em "SSH public key source" (Fonte da chave pública SSH), selecione ```Generate new key pair``` (gere um novo par de chaves).

- Em "Key pair name", digite ```Web-Server_key```.

**Inbound port rules (Regras de portas de entrada)**:

- Em "Public inbound ports" (Portas públicas de entrada), selecione: ```Allow selected ports``` (Permitir portas selecionadas).

- Em "Select inbound ports" (Selecione portas de entrada), selecione: ```HTTP (80)``` e ```SSH (22)```.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-13_48_59.png"></div>
    <div><span>Configuração da seção 'Basics' da máquina virtual que será criada</span></div>
</div>
</p>

E clique no botão "Next : Disks >" (Próximo: Discos).

**OS disk (Disco de Sistema Operacional)**:

- Em "OS disk type" (tipo de disco de sistema operacional), selecione ```Standard HDD (locally-redundant storage)```.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-13_58_48.png"></div>
    <div><span>Configuração da seção 'Disks' da máquina virtual que será criada</span></div>
</div>
</p>

E clique no botão "Next : Networking >" (Próximo: Rede).

**Network interface (Interface de rede)**:

- Em "Public IP" (IP Público), selecione ```(new) Web-Server-ip```, caso não exista, clique em "Create new". E uma aba à direita abrirá.

**Create public IP address (Criar endereço IP público)**:

Em "Name", coloque ```Web-Server-ip```.

Em "SKU", selecione "Basic".

Em "Assignment", selecione ```Static``` (Estático).

E clique em "OK".

- Marque a checkbox "Delete public IP and NIC when VM is deleted".

Clique no botão "Next : Management >" (Próximo: Gerenciamento).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_02_19.png"></div>
    <div><span>Configuração da seção 'Networking' da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Next : Monitoring >" (Próximo: Monitoramento).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_04_53.png"></div>
    <div><span>Configuração da seção 'Management' da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Next : Advanced >" (Próximo: Avançado).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_07_34.png"></div>
    <div><span>Configuração da seção 'Monitoring' da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Next : Tags >" (Próximo: Tags).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_10_15.png"></div>
    <div><span>Configuração da seção 'Advanced' da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Review + create" (Revisar + Criar).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_12_26.png"></div>
    <div><span>Configuração da seção 'Tags' da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Create" (Criar).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_15_12.png" alt="Review da máquina virtual que será criada:
Price
1 X Standard B1ls
by Microsoft
Terms of usePrivacy policy
Subscription credits apply
0.0052 USD/hr
Pricing for other VM sizes
TERMS
By clicking 'Create', I (a) agree to the legal terms and privacy statement(s) associated with the Marketplace offering(s) listed above; (b) authorize Microsoft to bill my current payment method for the fees associated with the offering(s), with the same billing frequency as my Azure subscription; and (c) agree that Microsoft may share my contact, usage and transactional information with the provider(s) of the offering(s) for support, billing and other transactional activities. Microsoft does not provide rights for third-party offerings. See the Azure Marketplace Terms for additional details.
Name
Preferred e-mail address
Preferred phone number
Basics
Subscription
Azure for Students
Resource group
(new) Web-Server_group
Virtual machine name
Web-Server
Region
East US
Availability options
No infrastructure redundancy required
Security type
Trusted launch virtual machines
Enable secure boot
Yes
Enable vTPM
Yes
Integrity monitoring
No
Image
Ubuntu Server 20.04 LTS - Gen2
VM architecture
x64
Size
Standard B1ls (1 vcpu, 0.5 GiB memory)
Enable Hibernation (preview)
No
Authentication type
SSH public key
Username
azureuser
Key pair name
Web-Server_key
Public inbound ports
SSH, HTTP
Azure Spot
No
Disks
OS disk size
Image default
OS disk type
Standard HDD LRS
Use managed disks
Yes
Delete OS disk with VM
Enabled
Ephemeral OS disk
No
Networking
Virtual network
(new) Web-Server-vnet
Subnet
(new) default (10.0.0.0/24)
Public IP
(new) Web-Server-ip
Accelerated networking
Off
Place this virtual machine behind an existing load balancing solution?
No
Delete public IP and NIC when VM is deleted
Enabled
Management
Microsoft Defender for Cloud
Basic (free)
System assigned managed identity
Off
Login with Microsoft Entra ID
Off
Auto-shutdown
Off
Backup
Disabled
Enable hotpatch
Off
Patch orchestration options
Azure-orchestrated patching (preview): patches will be installed by Azure
Reboot setting
Reboot if required
Monitoring
Alerts
Off
Boot diagnostics
On
Enable OS guest diagnostics
Off
Enable application health monitoring
Off
Advanced
Extensions
None
VM applications
None
Cloud init
No
User data
No
Disk controller type
SCSI
Proximity placement group
None
Capacity reservation group
None
"></div>
    <div><span>Review da máquina virtual que será criada</span></div>
</div>
</p>

Clique no botão "Download private key and create resource" (Baixar chave privada e criar recurso), e salve a chave privada em um diretório de sua preferência.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_29_52.png" alt="Caixa de aviso: 'Generate new key pair'"></div>
    <div><span></span></div>
</div>
</p>

Será mostrado a mensagem "Deployment is in progress" (Implantação está em progresso).

Aguarde até aparecer a mensagem "Your deployment is complete" (Sua implantação está completa).

E clique no botão "Go to resource" (Ir para o recurso).

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/screencapture-portal-azure-2024-04-23-14_32_31.png" alt="Menu de deployment com mensagem 'Your deployment is complete', com os botões: 'Go to resource', 'Create another VM'"></div>
    <div><span>Menu de deployment com mensagem 'Your deployment is complete'</span></div>
</div>
</p>

Será mostrada a máquina virtual recém-criada.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Criar_maquina_virtual/Screenshot 2024-04-23 at 14-33-16 Microsoft Azure.png" alt="Menu Overview da máquina virtual recém-criada. No sub-menu 'Essentials' contém o atributo 'Public IP address', que neste exemplo é 172.190.229.207"></div>
    <div><span>Menu Overview da máquina virtual recém-criada</span></div>
</div>
</p>

Nesse menu, em "**Overview**", em "**Essentials**", em "**Public IP address**", copie o endereço IP público para a área de transferênca.

Em um editor de texto de sua preferência, cole esse endereço IP. Em breve ele será utilizado.

### STEP 3 - Instalação do servidor web

Abra uma janela do Terminal (no Windows 10 é o PowerShell).

1. Utilize o comando ```cd``` para mudar de diretório para a pasta onde foi baixado a chave privada:

```
cd <PASTA ONDE FOI BAIXADO A CHAVE PRIVADA>
```

substituindo ```<PASTA ONDE FOI BAIXADO A CHAVE PRIVADA>``` pela pasta onde foi baixado a chave privada.

Exemplo:

```
cd Downloads
```

2. Utilize o comando ```ssh``` para acessar a máquina virtual no Azure:

```
ssh -i <NOME DO ARQUIVO DE CHAVE PRIVADA> <NOME DE USUARIO DA MAQUINA VIRTUAL AZURE>@<ENDEREÇO IP DA MÁQUINA VIRTUAL AZURE>
```

substituindo ```<NOME DO ARQUIVO DE CHAVE PRIVADA>``` pelo nome de arquivo da chave privada da máquina virtual do Azure,

substituindo ```<NOME DE USUARIO DA MAQUINA VIRTUAL AZURE>``` pelo nome de usuário da máquina virtual do Azure,

substituindo ```<ENDEREÇO IP DA MÁQUINA VIRTUAL AZURE>``` pelo endereço IP da máquina virtual do Azure.

O nome de usuário que criamos para a máquina virtual do Azure foi ```azureuser```.

Exemplo:

```
ssh -i ./Web-Server_key.pem azureuser@172.190.229.207
```

Esse é a saida esperada:

```
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.15.0-1060-azure x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

  System information as of Tue Apr 23 18:21:00 UTC 2024

  System load:  0.01              Processes:             100
  Usage of /:   5.2% of 28.89GB   Users logged in:       0
  Memory usage: 63%               IPv4 address for eth0: 10.0.0.4
  Swap usage:   0%


Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


The list of available updates is more than a week old.
To check for new updates run: sudo apt update
New release '22.04.3 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Tue Apr 23 18:18:52 2024 from 186.248.79.100
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

azureuser@Web-Server:~$
```

3. Na máquina virtual, digite os seguintes comandos:

```
sudo apt update
```

O comando ```sudo apt update``` faz o gerenciador de pacotes APT do Ubuntu obter informações dos pacotes disponíveis para serem instalados.

```
sudo apt install apache2 -y
```

O comando ```sudo apt install apache2 -y``` faz o gerenciador de pacotes APT do Ubuntu instalar o servidor web Apache.

4. Acesse a página web do servidor:

Em um navegador web, na sua barra de endereço, digite:

```
http://<ENDEREÇO IP DA MÁQUINA VIRTUAL AZURE>
```

substituindo ```<ENDEREÇO IP DA MÁQUINA VIRTUAL AZURE>``` pelo endereço IP da máquina virtual do Azure.

<p>
<div style="border: 2px solid black; display: block;">
    <div><img src="Imagens/Configurar_servidor_web/Screenshot 2024-04-23 at 15-24-13 Apache2 Ubuntu Default Page It works.png" alt="Página web padrão do servidor web Apache com o título: 'Apache2 Ubuntu Default Page'"></div>
    <div><span>Página web padrão do servidor web Apache</span></div>
</div>
</p>

### Solução de problemas

#### Erro: "Warning: Unprotected private key file!"

Caso uma mensagem de erro "Warning: Unprotected private key file!" apareça:

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'Web-Server_key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "Web-Server_key.pem": bad permissions
azureuser@172.190.229.207: Permission denied (publickey).
```

Digite o seguinte comando:

```
chmod 600 <NOME DO ARQUIVO DE CHAVE PRIVADA>
```

Exemplo:

```
chmod 600 Web-Server_key.pem
```

#### O comando ```apt update``` está demorando demais para finalizar

Na janela do terminal aperte as seguintes teclas:

```Ctrl + C``` ou ```Command + C``` (no Mac).

E digite o comando novamente.