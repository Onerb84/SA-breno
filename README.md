# Testes Automatizados com Cypress – Projeto RACK+

Este repositório contém testes automatizados end-to-end (E2E) utilizando **Cypress** para validação das funcionalidades principais do sistema **RACK+**, incluindo login, responsividade, navegação e estrutura da homepage.

---

## Estrutura do Projeto

cypress/
└── e2e/
├── login/
│ ├── login.cy.js
│ └── loginhtml.html
│
├── homepage/
│ ├── homepage.cy.js
│ └── homepagehtml.html
│
└── support/
├── commands.js
└── e2e.js

cypress.config.js
package.json
README.md


---

# Testes Implementados

---

# Testes da Página de Login

Arquivo: `cypress/e2e/login/login.cy.js`

## Login bem-sucedido
- Preenche e-mail e senha válidos  
- Clica em **Entrar**  
- Redireciona para `homepagehtml.html`

## Credenciais incorretas
- Insere email ou senha errados  
- Exibe mensagem: **"E-mail ou senha incorretos."**  
- Cor da mensagem: vermelha  
- Não redireciona

## Campos vazios
- Clica em entrar sem preencher os campos  
- Exibe: **"Por favor, preencha todos os campos."**  
- Cor vermelha  
- Permanece na página de login

## Ícone de mostrar/ocultar senha
- Campo inicia como `password`  
- Clicando no ícone do olho:
  - Troca para `text`  
  - Ícone muda para `bi-eye`
- Clicando novamente:
  - Volta para `password`
  - Ícone muda para `bi-eye-slash`

---

# Testes da Homepage

Arquivo: `cypress/e2e/homepage/homepage.cy.js`

---

## Layout Desktop (1024px)

### Barra lateral
- Visível  
- Largura: **90px**  
- Conteúdo com `margin-left: 90px`  
- Menu mobile oculto

### Navegação lateral
- Contém **6 links**  
- Título principal: **Salas**  
- Ícone de usuário visível

---

## Layout Mobile (412px)

### Menu superior mobile
- Visível com classe `sticky-top`  
- Barra lateral desktop oculta

### Menu mobile
- Abre ao clicar no ícone  
- Largura: **90px**  
- Possui **5 links**  
- Contém ícones: Home, Dashboard, Documentos, Configurações  
- Botão de fechar funcional

### Campo de pesquisa mobile
- Campo de pesquisa visível no conteúdo principal

---

##  Testes dos Cards

### Quantidade de cards
- Deve haver **6 cards** na grid

### Estrutura dos cards
Cada card deve conter:
- Link para vídeo placeholder no YouTube  
- Imagem da sala  
- Nome da sala em **negrito**  
- Indicador de status com:
  - Formato circular (`border-radius: 50%`)
  - Borda sólida

---

#  Requisitos

- **Node.js** 16+
- **NPM** ou **Yarn**
- Servidor local (Live Server recomendado)
- Cypress instalado

---

#  Como Rodar os Testes

## 1. Instale as dependências
```bash
npm install

## 2. Abra a interface do Cypress
npx cypress open

Selecione:

E2E Testing

Navegador

Testes:

login.cy.js

homepage.cy.js

## 3. Rodar via terminal
npx cypress run


## Observações

Os arquivos HTML devem estar acessíveis localmente nos caminhos configurados.

Alterações no HTML/CSS podem exigir atualização dos testes.

Testes validam comportamento funcional e visual.

## Conclusão

Os testes garantem:

Funcionamento correto do login

Responsividade em mobile e desktop

Navegação funcional

Estrutura correta dos cards

A automação reduz falhas e mantém a estabilidade da aplicação.
