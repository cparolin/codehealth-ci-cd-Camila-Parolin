# codehealth-ci-cd-Camila-Parolin
Atividade Prática de Introdução a Engenharia de Software

## Projeto HTML
O projeto anexado é uma tabela nutricional desenvolvida na aula de fundamentos de web


## Fluxo do Pipeline CI (GitHub Actions)

Este repositório contém um pipeline simples de Integração Contínua (CI) configurado no GitHub Actions, localizado em `.github/workflows/ci.yml`.

### Gatilho
O workflow é executado automaticamente **a cada push na branch `develop`**.

### Etapas do Pipeline

1. **Build**  
   - Simula a compilação do projeto com `echo "Compilando..."`.

2. **Testes**  
   - Simula a execução de testes automatizados.
   - Se encontrar a palavra **"erro"** no `README.md`, o teste falha.

3. **Relatório**  
   - Exibe mensagem de sucesso ou falha conforme o resultado dos testes.

4. **Deploy (Homologação)**  
   - Executado **somente se os testes passarem**.  
   - Simula a geração de um artefato `.zip` dentro da pasta `staging/`.

### Fluxo Resumido

Push na branch develop
       ↓
Build (simulado)
       ↓
Testes (simulados)
       ↓
Se falhar → mostra "Test failed"
Se passar → gera staging/app_homologacao.zip

## Motivo para não versionar credenciais

O arquivo `config.env` contém **variáveis de ambiente simuladas** (como usuários, senhas e chaves de API).  
Essas informações **não devem ser versionadas** nem enviadas ao repositório, pois podem expor dados sensíveis do sistema.

Por isso:  
- O arquivo foi adicionado ao `.gitignore`, garantindo que o Git o **ignore automaticamente**.  
- Em ambientes reais, **credenciais e segredos devem ser armazenados de forma segura**, como em **GitHub Secrets**, **variáveis de ambiente do servidor** ou **serviços de gerenciamento de segredos** (ex.: *AWS Secrets Manager*).

## Estrutura de Branches

- **main**: branch principal, usada para armazenar o código estável e pronto para produção.  
- **develop**: branch de desenvolvimento, onde as alterações são testadas e o pipeline CI é executado automaticamente.  

O fluxo de trabalho segue o padrão:

## Execução do Workflow

Abaixo está um exemplo da execução automática do pipeline no GitHub Actions:

<img width="1015" height="720" alt="Captura de Tela 2025-11-07 às 20 36 49" src="https://github.com/user-attachments/assets/3fc14a10-5367-44fe-9502-6458c70ff954" />

---

## Perguntas Reflexivas

### Qual é a principal vantagem da Integração Contínua para o trabalho em equipe?

A principal vantagem da **Integração Contínua (CI)** é permitir que todos os membros da equipe integrem suas alterações com frequência, garantindo que o código seja testado e validado automaticamente.  
Isso **reduz conflitos de integração**, **detecta erros cedo** e **mantém o projeto sempre em um estado funcional**, facilitando a colaboração entre desenvolvedores.

---

### Quais são os riscos que surgem se a Gerência de Configuração for negligenciada?

Se a **Gerência de Configuração** for negligenciada, podem ocorrer **erros de versão**, **perda de rastreabilidade**, **falhas em deploys** e **inconsistência entre ambientes**.  
Sem controle sobre o que foi alterado, por quem e em qual versão, o projeto se torna difícil de manter e propenso a falhas graves em produção.

---

### Como a automação pode aumentar a segurança das entregas?

A **automação** aumenta a segurança das entregas ao **padronizar o processo de build, teste e deploy**, reduzindo erros humanos.  
Ela garante que todas as etapas sejam executadas da mesma forma em cada entrega, incluindo **verificações automáticas**, **testes de qualidade** e **validações de segurança**, tornando o ciclo de entrega mais confiável e auditável.



