# Lab GitHub Actions Vars

## Perguntas de Reflexao

### 1. Por que a Secret aparece como `***` e a variavel aparece normalmente?

O GitHub Actions automaticamente esconde (mask) o valor de `secrets.*` nos logs para evitar vazamento de dados sensiveis. Ja as `vars.*` sao consideradas nao sensiveis e aparecem normalmente.

### 2. O Job `deploy_app` consegue ler a variavel `BUILD_VERSION` criada no Job `build_app`? Por que?

Nao, porque cada job roda em um runner (maquina) novo e independente. Variaveis de ambiente de um job nao sao compartilhadas com outro, a menos que voce use `artifacts` ou `outputs` explicitamente.
