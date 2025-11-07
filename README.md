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

## 📸 Execução do Workflow

Abaixo está um exemplo da execução automática do pipeline no GitHub Actions:

![Execução do Workflow](screenshot_workflow.png)




