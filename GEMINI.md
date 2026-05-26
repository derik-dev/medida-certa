# GEMINI.md - Clínica Medida Certa

Este arquivo serve como guia de contexto e instruções para o desenvolvimento e manutenção do projeto **Clínica Medida Certa**.

## 1. Visão Geral do Projeto
O projeto é um website institucional (Landing Page) para a **Clínica Medida Certa**, uma clínica de saúde focada em atendimento humanizado e acessível. O site destaca especialidades como Psicologia, Nutrição, Geriatria e Neuropsicologia.

### Tecnologias Principais
- **Front-end:** HTML5, CSS3, JavaScript (ES6+).
- **Estilização:** [Tailwind CSS](https://tailwindcss.com/) (via CDN) para utilitários rápidos e CSS Customizado em `style.css` para componentes complexos e variáveis globais.
- **Animações:** [GSAP](https://greensock.com/gsap/) com [ScrollTrigger](https://greensock.com/scrolltrigger/) para revelações e interatividade cinética.
- **Scroll Suave:** [Lenis](https://github.com/darkroomengineering/lenis) para uma experiência de rolagem refinada.
- **Carrossel:** [Swiper.js](https://swiperjs.com/) para depoimentos e cards de resultados.
- **Inteligência Artificial:** Chatbot integrado com a API da [Groq](https://groq.com/) (modelo Llama 3.3).

## 2. Estrutura de Arquivos
- `index.html`: Estrutura principal do site, incluindo links para bibliotecas externas e seções da página.
- `style.css`: Variáveis de cores (conforme briefing), fontes, componentes personalizados (cards, botões, glassmorphism) e ajustes de layout.
- `script.js`: Lógica de animação GSAP, inicialização do Lenis e Swiper, e implementação do Chatbot.
- `briefing.md`: Documento de referência com a identidade visual, público-alvo e tom de comunicação da marca.

## 3. Comandos e Execução
Como o projeto é composto por arquivos estáticos, não há um processo de build complexo no momento.

### Execução Local
- Abra o arquivo `index.html` diretamente em qualquer navegador moderno.
- Recomenda-se o uso de extensões como **Live Server** (VS Code) para recarregamento automático durante o desenvolvimento.

### TODO / Próximos Passos
- [ ] Migrar a chave de API da Groq para um ambiente seguro (Backend/Variables).
- [ ] Atualizar links de contato (WhatsApp/Instagram) com os dados reais da clínica.
- [ ] Consolidar estilos inline do HTML para o `style.css`.
- [ ] Otimizar o carregamento de imagens externas.

## 4. Convenções de Desenvolvimento
- **Nomenclatura:** Seguir o padrão de classes do Tailwind sempre que possível. Para componentes customizados, utilizar prefixos descritivos (ex: `.spec-card`, `.chat-bubble`).
- **Cores:** Utilizar as variáveis definidas no `:root` do `style.css` (ex: `--azul-clinico`, `--verde-suave`) para manter a consistência com o briefing.
- **Responsividade:** Priorizar o uso das classes utilitárias do Tailwind (`md:`, `lg:`, `xl:`) para garantir que o site funcione bem em dispositivos móveis.
- **Acessibilidade:** Garantir que imagens tenham `alt` descritivo e que o contraste de cores atenda aos padrões básicos de leitura.

---
*Este documento deve ser atualizado conforme novas funcionalidades ou mudanças arquiteturais forem implementadas.*
