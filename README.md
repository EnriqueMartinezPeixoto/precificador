# 🏷️ Precificador (Edição Global)

O **Precificador** é uma ferramenta de precificação inteligente e de página única (Single Page Application), projetada para eliminar a incerteza financeira na hora de vender produtos ou serviços. Seja você um desenvolvedor web vendendo sites, um artesão, confeiteiro ou freelancer, esta calculadora consolida todos os seus custos variáveis e fixos para sugerir o preço de venda ideal.

A versão atual introduz uma arquitetura de internacionalização (i18n) construída do zero e suporte global a moedas, permitindo que a aplicação seja utilizada por empreendedores em diferentes regiões do mundo sem a necessidade de recarregar a página ou instalar dependências.

---

## ✨ Recursos e Funcionalidades Detalhadas

*   **🌐 Motor Multilíngue Nativo (i18n):** O aplicativo possui suporte nativo para Português (pt-BR), Inglês (en-US) e Espanhol (es-ES). A troca de idiomas ocorre em tempo real, varrendo o DOM e substituindo strings baseadas em um dicionário de dados local, oferecendo uma experiência fluida sem recarregamentos de página.
*   **💱 Conversão e Formatação Monetária Inteligente:** Suporte nativo para Real (BRL), Dólar (USD), Euro (EUR), Libra (GBP), Peso Argentino (ARS) e Peso Mexicano (MXN). O motor utiliza a API `Intl.NumberFormat` vinculada ao idioma ativo, o que significa que o formato numérico (uso de vírgulas ou pontos para decimais) se adapta automaticamente às regras gramaticais do idioma selecionado pelo usuário.
*   **📦 Gestão Dinâmica de Materiais:** Um sistema de linhas dinâmicas permite adicionar múltiplos insumos ao cálculo. Você informa o valor pago por uma quantidade fechada (ex: R$ 50,00 por 1kg) e o sistema extrai o custo exato da fração utilizada no lote (ex: 200g), evitando desperdícios no cálculo.
*   **⏱️ Precificação de Mão de Obra:** O tempo não é gratuito. A calculadora integra as horas investidas na produção do lote e cruza essa informação com o valor desejado da sua hora de trabalho, garantindo que o seu esforço físico e mental seja remunerado antes mesmo da aplicação da margem de lucro.
*   **📊 Proteção de Margem e Taxas Ocultas:** Muitos empreendedores perdem dinheiro por não calcularem as taxas de plataformas de pagamento (cartão de crédito, Mercado Pago, Stripe). O Precificador isola essas taxas percentuais, junto com os impostos, garantindo que a sua **margem de lucro desejada** seja o valor líquido que realmente sobra no seu bolso.

---

## 🚀 Tecnologias e Arquitetura

Este projeto foi desenhado sob o princípio do **Zero-Build**. Ele não necessita de Node.js, Webpack, React ou qualquer framework pesado para rodar. Tudo funciona no lado do cliente (Client-Side).

*   **HTML5 Semântico:** Estrutura acessível com formulários bem definidos e otimização para leitores de tela (`aria-labels`).
*   **CSS3 Moderno:** 
    *   Design totalmente responsivo usando `CSS Grid` e `Flexbox`.
    *   Gerenciamento de temas (Dark/Light Mode) integrado via **CSS Custom Properties (Variáveis)** e `prefers-color-scheme`.
*   **JavaScript Vanilla (ES6+):** 
    *   Manipulação de estado simplificada.
    *   Delegação de eventos (Event Delegation) para otimizar o desempenho de botões gerados dinamicamente.
    *   Isolamento de escopo via IIFE (Immediately Invoked Function Expression) para não poluir o escopo global do navegador.

---

## 🧠 Como Funciona a Internacionalização (i18n)

Para evitar dependências como `i18next`, o sistema utiliza um objeto literal no JavaScript que atua como banco de dados de traduções. 

As tags HTML recebem um atributo customizado (ex: `<span data-i18n="lblTax">Impostos</span>`). Quando o usuário seleciona um novo idioma, o JavaScript dispara a função `updateLanguage()`, que localiza todos os elementos com o atributo `[data-i18n]` e substitui o seu `textContent` pela string correspondente no dicionário ativo, atualizando a interface instantaneamente.

---

## 📦 Como Usar e Hospedar

Como a aplicação é um arquivo HTML estático (com CSS e JS embutidos), o processo de execução é imediato:

**Uso Local:**
1. Faça o download ou clone este repositório: `git clone https://github.com/seu-usuario/precificador.git`
2. Navegue até a pasta do projeto.
3. Dê um duplo clique no arquivo `index.html` para abri-lo em qualquer navegador moderno.

**Hospedagem em Produção:**
Você pode colocar esta ferramenta no ar em menos de 1 minuto, de forma 100% gratuita:
*   **GitHub Pages:** Faça o commit do arquivo `index.html` em um repositório público e ative o GitHub Pages nas configurações.
*   **Vercel / Netlify:** Arraste e solte a pasta do projeto diretamente no painel dessas plataformas.

---

## 🤝 Como Contribuir

Contribuições são muito bem-vindas, especialmente para adicionar novos idiomas, moedas ou refinar a lógica de cálculo! Para contribuir:

1. Faça um **Fork** do projeto.
2. Crie uma branch para sua feature: `git checkout -b feature/novo-idioma-frances`
3. Adicione o novo bloco de tradução na constante `dict` dentro da tag `<script>`.
4. Faça o commit das suas alterações: `git commit -m 'feat: adiciona suporte ao idioma Francês'`
5. Faça o push para a branch: `git push origin feature/novo-idioma-frances`
6. Abra um **Pull Request**.

---

## 📄 Licença

Este projeto é distribuído sob a licença MIT. Isso significa que você é livre para usar, modificar, distribuir e até mesmo utilizar comercialmente este código, desde que mantenha o aviso de direitos autorais original.
