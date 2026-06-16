# 🚀 Gerenciamento de Instâncias Amazon EC2 na AWS

Este repositório foi desenvolvido como parte de um desafio prático na plataforma [DIO](https://dio.me), com o objetivo de consolidar conhecimentos essenciais sobre o provisionamento, configuração e gerenciamento de servidores virtuais na nuvem utilizando o **Amazon EC2 (Elastic Compute Cloud)**.

---

## 🎯 Objetivos do Projeto
*   **Provisionar** instâncias EC2 utilizando as boas práticas de segurança da AWS.
*   **Configurar** redes básicas e regras de firewall através de Security Groups.
*   **Documentar** de forma clara e estruturada todo o processo técnico.
*   **Utilizar o GitHub** como portfólio e ferramenta de compartilhamento de documentação técnica.

---

## 🛠️ Tecnologias e Conceitos Utilizados
*   **AWS Management Console**: Interface gráfica para gerenciamento dos recursos em nuvem.
*   **Amazon EC2**: Servidores virtuais na nuvem (Instâncias).
*   **Amazon Machine Image (AMI)**: Modelos de sistemas operacionais (ex: Ubuntu Server, Amazon Linux).
*   **Key Pairs (Pares de Chaves)**: Chaves criptográficas para acesso SSH seguro (arquivos `.pem` ou `.ppk`).
*   **Security Groups**: Firewall virtual para controlar o tráfego de entrada e saída.

---

## 📋 Passo a Passo da Implementação

### 1. Criação e Configuração da Instância EC2
1.  Acesse o Console AWS e navegue até o serviço **EC2**.
2.  Clique em **Launch Instance** (Executar Instância).
3.  **Nome do Servidor**: Defina uma tag de nome clara para identificação.
4.  **AMI (Sistema Operacional)**: Selecionado o `Ubuntu Server 24.04 LTS` (elegível para o nível gratuito).
5.  **Tipo de Instância**: Escolhido `t2.micro` (ou `t3.micro` dependendo da região) para manter os custos no *Free Tier*.

### 2. Segurança e Acesso Remoto
1.  **Key Pair**: Criação de uma nova chave RSA em formato `.pem` para acesso via terminal SSH.
2.  **Network Settings (Security Group)**:
    *   Criado um novo grupo de segurança.
    *   Liberada a porta **22 (SSH)** apenas para o IP atual, garantindo segurança administrativa.
    *   *(Opcional)* Liberadas as portas **80 (HTTP)** e **443 (HTTPS)** para tráfego web geral.

### 3. Inicialização e Conexão
1.  A instância foi executada com sucesso e monitorada até o status `Running` (Executando).
2.  A conexão foi realizada via terminal SSH utilizando o comando:
    ```bash
    ssh -i "sua-chave.pem" ubuntu@seu-ip-publico-ec2
    ```

---

## 💡 Insights e Aprendizados Adquiridos
*   **Segurança em Primeiro Lugar**: Nunca se deve abrir a porta SSH (22) para o mundo (`0.0.0.0/0`). O ideal é restringir ao seu IP público atual ou usar soluções como o *AWS Systems Manager Session Manager*.
*   **Gestão de Custos**: É fundamental monitorar o uso do Free Tier e lembrar de **interromper (Stop)** ou **encerrar (Terminate)** as instâncias que não estão mais em uso para evitar cobranças indesejadas.
*   **Criptografia**: O par de chaves gerado é a única forma de acessar o servidor inicialmente. Perder a chave privada significa perder o acesso administrativo direto ao SO da instância.

---

## 🗂️ Evidências Práticas
*(Dica: Se você tirou prints, salve na pasta /images do seu repositório e remova os comentários abaixo)*

| Tela do Dashboard EC2 | Acesso via Terminal |
| :---: | :---: |
| ![Dashboard EC2](./images/ec2-dashboard.png) | ![Conexão SSH](./images/ec2-connected.png) |

---

## 📚 Links Úteis Utilizados
*   [Documentação Oficial: Gerenciando instâncias EC2 da Amazon](https://amazon.com)
*   [Guia Prático de Markdown do GitHub](https://github.com)

---
Feito com 💻 por [Seu Nome](https://github.com)
