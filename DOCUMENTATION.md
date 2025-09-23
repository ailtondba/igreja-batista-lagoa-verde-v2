# Documentação Técnica - Igreja Batista Regular de Lagoa Verde

## Visão Geral Técnica

Este documento fornece uma visão técnica detalhada do website da Igreja Batista Regular de Lagoa Verde, incluindo arquitetura, tecnologias implementadas, estrutura de código e funcionalidades.

## Arquitetura do Sistema

### Tecnologias Implementadas

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Hospedagem**: Firebase Hosting
- **CDN**: Font Awesome 6.4.0 para ícones
- **Responsividade**: CSS Grid e Flexbox
- **Armazenamento Local**: LocalStorage para persistência de tema

### Estrutura de Código

#### HTML5 Semântico
- Uso de tags semânticas (`<header>`, `<nav>`, `<section>`, `<footer>`)
- Meta tags otimizadas para SEO
- Estrutura acessível com atributos ARIA

#### CSS3 Moderno
- CSS Grid e Flexbox para layouts responsivos
- Custom Properties (CSS Variables) para temas
- Media queries para responsividade
- Animações e transições suaves

#### JavaScript ES6+
- Módulos e funções arrow
- Event listeners modernos
- LocalStorage para persistência
- Manipulação dinâmica do DOM

## Funcionalidades Detalhadas

### 1. Sistema de Temas (Claro/Escuro)

**Implementação:**
```javascript
function toggleTheme() {
    const body = document.body;
    const themeIcon = document.getElementById('theme-icon');
    
    body.classList.toggle('dark-theme');
    
    if (body.classList.contains('dark-theme')) {
        themeIcon.innerHTML = '&#x263D;'; // Lua
        localStorage.setItem('theme', 'dark');
    } else {
        themeIcon.innerHTML = '&#x263C;'; // Sol
        localStorage.setItem('theme', 'light');
    }
}
```

**Características:**
- Persistência no LocalStorage
- Transições suaves entre temas
- Ícones dinâmicos (sol/lua)
- Aplicação automática ao carregar a página

### 2. Menu Responsivo

**Implementação:**
- Menu hambúrguer para dispositivos móveis
- Animações CSS com clip-path
- Event listeners para toggle e fechamento automático

**Breakpoints:**
- Desktop: > 768px
- Tablet: 768px - 480px
- Mobile: < 480px

### 3. Player de Rádio Integrado

**Funcionalidades:**
- Play/Pause com controle visual
- Controle de volume deslizante
- Stream de rádio online
- Interface minimalista

**Código:**
```javascript
const audio = document.getElementById("radio");
const playBtn = document.getElementById("playBtn");
const volume = document.getElementById("volume");

audio.volume = 0.1;
let isPlaying = true;

playBtn.addEventListener("click", () => {
    if (isPlaying) {
        audio.pause();
        playBtn.textContent = "▶";
    } else {
        audio.play();
        playBtn.textContent = "⏸";
    }
    isPlaying = !isPlaying;
});
```

### 4. Efeitos Visuais

**Header Dinâmico:**
- Sombra que aumenta com o scroll
- Posicionamento fixo
- Transições suaves

**Animações:**
- Fade-in para conteúdo principal
- Hover effects em botões e links
- Transições de tema

## Estrutura de Diretórios

```
/
├── index.html                 # Página principal
├── README.md                  # Documentação do projeto
├── DOCUMENTATION.md           # Esta documentação técnica
├── logo/
│   └── logo-igreja.png       # Logo da igreja (80x80px)
├── Principal/
│   ├── index.html            # Página principal alternativa
│   └── background.jpg        # Imagem de fundo hero (1920x1080px)
├── quem-somos/
│   └── index.html            # Página institucional
├── Ministérios/
│   └── index.html            # Página dos ministérios
├── Horarios/
│   └── index.html            # Página de horários de cultos
├── localização/
│   ├── index.html            # Página de localização
│   └── igreja-local.png      # Foto da igreja local
└── contacto/
    └── index.html            # Página de contato
```

## Configurações e Otimizações

### Performance

1. **Otimização de Imagens:**
   - Compressão adequada para web
   - Formatos otimizados (WebP quando possível)
   - Lazy loading implementado

2. **CSS Otimizado:**
   - Minificação em produção
   - Critical CSS inline
   - Media queries eficientes

3. **JavaScript:**
   - Código minificado
   - Event listeners otimizados
   - Carregamento assíncrono quando possível

### SEO e Acessibilidade

1. **Meta Tags:**
   ```html
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Igreja Batista Regular de Lagoa Verde</title>
   ```

2. **Semântica HTML:**
   - Uso correto de headings (h1, h2, h3)
   - Atributos alt em imagens
   - Estrutura lógica de navegação

3. **Acessibilidade:**
   - Contraste adequado de cores
   - Navegação por teclado
   - Atributos ARIA quando necessário

## Manutenção e Atualizações

### Estrutura de Desenvolvimento

1. **Versionamento:**
   - Git para controle de versão
   - Branches para features
   - Tags para releases

2. **Deploy:**
   - Firebase Hosting
   - Deploy automático via GitHub Actions
   - Ambiente de staging para testes

### Monitoramento

1. **Analytics:**
   - Google Analytics implementado
   - Métricas de performance
   - Relatórios de uso

2. **Performance:**
   - Lighthouse scores
   - Core Web Vitals
   - Monitoramento de uptime

## Troubleshooting

### Problemas Comuns

1. **Player de Rádio não funciona:**
   - Verificar URL do stream
   - Testar em diferentes navegadores
   - Verificar políticas de autoplay

2. **Tema não persiste:**
   - Verificar suporte ao LocalStorage
   - Limpar cache do navegador
   - Verificar JavaScript habilitado

3. **Menu mobile não abre:**
   - Verificar JavaScript carregado
   - Testar event listeners
   - Verificar CSS do menu

### Logs e Debug

```javascript
// Debug do tema
console.log('Tema atual:', localStorage.getItem('theme'));

// Debug do player
console.log('Estado do áudio:', audio.paused ? 'pausado' : 'tocando');

// Debug do menu
console.log('Menu ativo:', mainNav.classList.contains('active'));
```

## Contato Técnico

Para questões técnicas ou suporte:
- **Desenvolvedor**: [Nome do desenvolvedor]
- **Email**: [email@exemplo.com]
- **GitHub**: [github.com/usuario]

---

*Documentação atualizada em: Janeiro 2025*