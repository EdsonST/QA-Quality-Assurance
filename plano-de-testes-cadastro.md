# Plano de Testes – Cadastro de Usuário

## 1. Objetivo
Garantir que a funcionalidade de **cadastro de usuários** funcione conforme os requisitos definidos,
validando regras de negócio, campos obrigatórios, mensagens de erro e redirecionamento após sucesso.

---

## 2. Escopo

### Dentro do escopo
- Validação de campos obrigatórios
- Validação de nome completo
- Validação de e-mail
- Validação de usuário
- Validação de senha (mínimo de 8 caracteres)
- Validação de confirmação de senha
- Redirecionamento para tela de login após cadastro válido
- Exibição de mensagens de erro

### Fora do escopo
- Testes de performance
- Testes de segurança
- Testes de persistência em banco de dados

---

## 3. Critérios de Aceite
- Todos os campos são obrigatórios
- O nome deve conter **nome completo**
- O e-mail deve estar em formato válido
- A senha deve conter no mínimo 8 caracteres
- A confirmação de senha deve ser igual à senha
- Cadastro válido deve redirecionar para a tela de login
- Cadastro inválido deve exibir mensagem de erro clara

---

## 4. Estratégia de Teste
Serão realizados **testes manuais**, com foco em:
- Happy path
- Testes negativos
- Análise de valores de fronteira
- Testes exploratórios iniciais

---

## 5. Casos de Teste

### 5.1 Cenário Positivo (Happy Path)
- Cadastro com todos os campos válidos  
  **Resultado esperado:**  
  Usuário cadastrado com sucesso e redirecionado para a tela de login.

---

### 5.2 Campos Obrigatórios
- Nome vazio → erro
- E-mail vazio → erro
- Usuário vazio → erro
- Senha vazia → erro
- Confirmação de senha vazia → erro

---

### 5.3 Validação de Nome
- Apenas primeiro nome → erro
- Apenas sobrenome → erro
- Nome completo válido → sucesso (se demais campos válidos)

---

### 5.4 Validação de Senha (Análise de Fronteira)
- Senha com menos de 8 caracteres → erro
- Senha com exatamente 8 caracteres → sucesso
- Senha com mais de 8 caracteres → sucesso

---

### 5.5 Confirmação de Senha
- Senha diferente da confirmação → erro

---

### 5.6 Validação de E-mail
- E-mail em formato inválido → erro
- E-mail válido → sucesso (se demais campos válidos)

---

## 6. Observações
Este plano de testes foi criado com foco em **priorização por risco**, garantindo cobertura dos fluxos
críticos da funcionalidade de cadastro dentro de um cenário real de restrição de tempo.
