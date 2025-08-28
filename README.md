# Desafio de Projeto: Criando máquinas Virtuais na Azure

No seguinte desafio o aluno é desafiado a criar uma VM (máquina virtual) 

## Início Rápido: Criar uma Máquina Virtual Linux no Azure

Eu usei o guia presente em [Início Rápido: Criar uma máquina virtual do Windows no Portal do Azure](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal) para criar a máquina virtual, sendo que em vez de criar para Windows, eu criei com a imagem Ubuntu 24.04 LTS. Assim criei uma VM no **Portal do Azure** e fiz o acesso via SSH.

---

### Pré-requisitos
- Ter uma assinatura do Azure (ou criar uma conta gratuita).  
- Estar em sistema operacional Linux
---

### Etapas Principais

#### 1. Entrar no Azure
- Acesse o [Portal do Azure](https://portal.azure.com).  

#### 2. Criar a VM

- Pesquise por **Máquinas virtuais** > **Criar** > **Máquina virtual do Azure**.  
- Configure:  
  - **Nome:** `myVM`  
  - **Imagem:** *Ubuntu Server 24.04 LTS - x64 Gen2 (serviços gratuitos qualificados)*
  - **Usuário:** `azureuser`
  - **Portas:** habilite **SSH (22)** 
- Clique em **Examinar + Criar** e depois em **Criar**
- Ao criar, receberá um arquivo `.pem` que é a chave de acesso à VM via SSH.


Há mais opções de costumização da VM, sendo eles:
- **Opções de disponibilidade**
- **Opções de zona**
- **Zona de disponibilidade**
- **Tipo de segurança**
- **Arquitetura de VM**
- **Executar com desconto de Spot do Azure**
- **Tamanho**
- **Habilitar Hibernação**
- **Tipo de Autenticação**
- **Origem de chave SSH Pública**
- **Tipo de Chave SSH**
- **Nome do par de chaves**
- **Portas de entrada públicas**
- **Selecione as portas de entrada**
<br>

- **Páginas de criação da VM**
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-51-43.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-05.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-14.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-22.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-27.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-32.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-52-38.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-53-26.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-54-19.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-55-08.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-55-26.png)

#### 3. Conectar via SSH
Um dos requisitos para conexão via SSH é ter gerado uma chave SSH, se não a tiver, segue o passo a passo do GitHub no link [Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) para gerar a chave.
Assim, sabendo o caminho para onde baixou a chave `.pem` da VM, 
- Vá até o diretório da chave: `cd /caminho/para/diretorio/`
- Faça com que apenas o dono possa ler/escrever a chave privada: `chmod 600 nome_chave.pem`
- Na página da VM, selecione **Conectar**.  
- No terminal do Linux (Ubuntu), rode: `ssh -i /caminho/para/diretorio/nome_chave.pem azureuser@endereco_da_vm` obs.: o `azureuser` é o nome de usuário que foi criado na VM 
- Aceite o aviso de certificado, se aparecer.
<br>

- **Imagens da conexão com VM**
![foto](images/Captura%20de%20tela%20de%202025-08-28%2014-57-21.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2015-09-00.png)
![foto](images/Captura%20de%20tela%20de%202025-08-28%2015-09-09.png) 

---

### Gerenciamento de Recursos

#### 🔹 Limpeza
- Vá ao **Grupo de Recursos** > **Excluir grupo de recursos**.  

#### 🔹 Desligamento Automático
- Acesse **Operações da VM > Desligamento automático**.  
- Defina horário e fuso correto (**padrão: UTC**).  

---

### Conclusão

A criação de uma máquina virtual no Azure demonstrou, de forma prática, como a plataforma possibilita a rápida disponibilização de recursos de infraestrutura em nuvem. Durante o processo, foi possível compreender as etapas essenciais — desde a configuração inicial da VM, escolha da imagem do sistema operacional, definição de usuário e portas de acesso, até a conexão segura via SSH.

Além disso, o desafio reforçou a importância de boas práticas de gerenciamento, como o uso correto das chaves de autenticação, a configuração de desligamento automático e a limpeza de recursos não utilizados, evitando custos desnecessários.

Em síntese, a experiência mostrou que o Azure oferece uma interface intuitiva e recursos flexíveis que permitem ao usuário criar, personalizar e administrar máquinas virtuais de forma ágil e segura. Esse exercício não apenas consolida conhecimentos técnicos, como também prepara o aluno para utilizar serviços de nuvem em cenários reais de desenvolvimento, testes e produção.