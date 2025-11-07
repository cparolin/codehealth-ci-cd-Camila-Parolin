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

