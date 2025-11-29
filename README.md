# ☁️ Desafio: Criação e Documentação de Máquina Virtual (VM) no Azure

Este projeto documenta a experiência prática de provisionamento de uma Máquina Virtual (VM) de IaaS (Infrastructure as a Service) no Microsoft Azure, consolidando conceitos de gerenciabilidade, custos e segurança de rede.

O objetivo é transformar a execução técnica em documentação estruturada, conforme o desafio proposto na Trilha de Cloud Computing.

---

## 🚀 Conceitos de Cloud Aplicados

A criação da VM no Azure demonstra a aplicação dos seguintes pilares do Cloud Computing:

| Conceito | Descrição no Projeto |
| :--- | :--- |
| **IaaS (Infrastructure as a Service)** | A VM é o exemplo clássico de IaaS. A Azure fornece o hardware, a rede e o armazenamento, enquanto o utilizador (nós) é responsável pela gestão do sistema operativo (Windows Server) e das aplicações. |
| **OpEx (Custo Operacional)** | A escolha do tamanho da VM e o modelo de consumo *pay-as-you-go* (pago pelo uso) representam o modelo OpEx, contrastando com o alto custo inicial do CapEx (compra de servidores físicos). |
| **Gerenciabilidade** | A criação de um **Grupo de Recursos** dedicado (`rg-vm-desafio`) e a gestão da VM através do Portal ou CLI ilustram a facilidade de controlo dos recursos na nuvem. |
| **Segurança (NSG)** | A configuração das **Regras de Porta de Entrada** (Network Security Group - NSG) na rede da VM garante que apenas o protocolo necessário (RDP/SSH) tenha acesso, atuando como a primeira linha de defesa. |
| **Elasticidade** | A capacidade de redimensionar a VM para um plano maior ou menor (*Scale Up* / *Scale Down*) instantaneamente, conforme a demanda, demonstra a elasticidade do ambiente Azure. |

---

## 📋 Passos da Criação e Configuração da VM

Os passos abaixo detalham a configuração realizada no Portal do Azure para a criação da Máquina Virtual.

### 1. Detalhes Básicos da Instância

| Configuração | Valor/Escolha | Propósito |
| :--- | :--- | :--- |
| **Grupo de Recursos** | `rg-vm-desafio` (Novo) | Agrupar todos os componentes (VM, Disco, IP, Rede) para fácil gestão e eliminação. |
| **Região** | Escolhida a região mais próxima (Ex: *Brazil South*) | Reduz a latência de acesso. |
| **Nome da VM** | `vm-desafio-dev` | Nome de identificação do ativo. |
| **Imagem (OS)** | Windows Server 2022 DataCenter | O sistema operativo que será gerenciado (IaaS). |
| **Tamanho (Size)** | `Standard D2s v3` (ou similar) | Define a capacidade de CPU e Memória (o custo OpEx). |

### 2. Credenciais de Administrador

* Definição de `username` e `password` para acesso remoto via RDP (para Windows) ou SSH (para Linux).

### 3. Configurações de Entrada e Rede (Segurança)

* **Portas de Entrada Públicas:** Permitir portas selecionadas.
* **Portas Selecionadas:** `RDP (3389)` ou `SSH (22)`.
* **NSG (Network Security Group):** O NSG foi criado para garantir que apenas esta porta específica (3389) tem permissão de entrada na rede virtual da VM.

### 4. Revisão e Provisionamento

Após validar que as configurações do disco e da rede virtual estão corretas, a VM foi provisionada. A Azure demorou alguns minutos para alocar todos os recursos e colocar o sistema operativo a funcionar.

---

## 🖼️ Capturas de Tela Relevantes (Opcional)

Se necessário, as capturas de tela foram organizadas e adicionadas à pasta `/images` para ilustrar os seguintes pontos:

* Tela de Configuração do Grupo de Recursos e Tamanho.
* Regras de Entrada (NSG) configuradas.
* Página de *Overview* da VM após a criação (com o IP público).

---

## 🔗 Links e Recursos Úteis

* **Comandos Git Essenciais:**
    ```bash
    git init
    git add .
    git commit -m "feat: conclusao do desafio azure vm"
    git remote add origin [https://www.youtube.com/watch?v=BW1w0P1KNk0](https://www.youtube.com/watch?v=BW1w0P1KNk0)
    git push -u origin main
    ```
* [Documentação Oficial: Criar uma máquina virtual do Windows no Portal do Azure](https://learn.microsoft.com/pt-br/azure/virtual-machines/windows/quick-create-portal)
