<<<<<<< HEAD
# 📚 Documentação Técnica - Igreja Batista Regular de Lagoa Verde

## 📖 Índice
- [Visão Geral](#visão-geral)
- [Arquitetura do Sistema](#arquitetura-do-sistema)
- [Tecnologias Implementadas](#tecnologias-implementadas)
- [Estrutura de Código](#estrutura-de-código)
- [Funcionalidades Detalhadas](#funcionalidades-detalhadas)
- [Configurações](#configurações)
- [Manutenção](#manutenção)
- [Troubleshooting](#troubleshooting)

## 🎯 Visão Geral

Este documento fornece uma visão técnica completa do website da Igreja Batista Regular de Lagoa Verde, incluindo detalhes de implementação, arquitetura e manutenção.

### Especificações Técnicas
- **Tipo:** Single Page Application (SPA) com múltiplas páginas
- **Arquitetura:** Frontend estático com JavaScript vanilla
- **Hospedagem:** Firebase Hosting
- **Performance:** Otimizado para Core Web Vitals
- **Compatibilidade:** Navegadores modernos (Chrome 80+, Firefox 75+, Safari 13+)

## 🏗️ Arquitetura do Sistema

### Estrutura de Diretórios
`
site/
├── 📄 index.html                    # Página principal (Landing)
├── 📁 contacto/                     # Módulo de contatos
│   └── index.html                   # Página de contatos com WhatsApp
├── 📁 Ministérios/                  # Módulo de ministérios
│   └── index.html                   # Informações dos ministérios
├── 📁 Horarios/                     # Módulo de horários
│   └── index.html                   # Cronograma de atividades
├── 📁 localização/                  # Módulo de localização
│   ├── index.html                   # Mapa e endereço
│   └── igreja-local.png             # Imagem da localização
├── 📁 Principal/                    # Página principal alternativa
│   ├── index.html                   # Layout alternativo
│   └── background.jpg               # Imagem de fundo
├── 📁 quem-somos/                   # Módulo institucional
│   └── index.html                   # História e missão
├── 📁 logo/                         # Assets visuais
│   └── logo-igreja.png              # Logotipo oficial
├── 📁 public/                       # Arquivos de produção
│   ├── README.md                    # Documentação do usuário
│   └── DOCUMENTATION.md             # Esta documentação
├── 📄 firebase.json                 # Configuração Firebase
├── 📄 .firebaserc                   # Projeto Firebase
└── 📄 .gitignore                    # Exclusões Git
`

## 💻 Tecnologias Implementadas

### Frontend Stack
`javascript
// Tecnologias Core
HTML5: {
  version: "Living Standard",
  features: ["Semantic Elements", "Accessibility", "SEO Meta Tags"]
}

CSS3: {
  version: "Level 4",
  features: ["Flexbox", "Grid", "Custom Properties", "Media Queries"],
  methodology: "BEM-inspired"
}

JavaScript: {
  version: "ES6+",
  type: "Vanilla JS",
  features: ["DOM Manipulation", "Local Storage", "Event Handling"]
}
`

### Bibliotecas Externas
`html
<!-- Font Awesome Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
`

### Infraestrutura
- **Firebase Hosting**: CDN global, SSL automático
- **Firebase Data Connect**: Preparado para futuras integrações
- **Domain**: code-49bf4.web.app (Firebase subdomain)

## 🔧 Estrutura de Código

### HTML Structure Pattern
`html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <!-- Meta Tags SEO -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="...">
    
    <!-- External Resources -->
    <link rel="stylesheet" href="...">
    
    <!-- Internal Styles -->
    <style>/* CSS interno */</style>
</head>
<body>
    <!-- Header fixo -->
    <header class="header">
        <nav class="nav">
            <!-- Menu responsivo -->
        </nav>
    </header>
    
    <!-- Conteúdo principal -->
    <main class="main">
        <!-- Seções específicas -->
    </main>
    
    <!-- Rodapé -->
    <footer class="footer">
        <!-- Informações e player -->
    </footer>
    
    <!-- Scripts -->
    <script>/* JavaScript interno */</script>
</body>
</html>
`

### CSS Architecture
`css
/* Reset e Base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Variáveis CSS (Custom Properties) */
:root {
    --primary-color: #2c3e50;
    --secondary-color: #3498db;
    --text-color: #333;
    --bg-color: #fff;
}

/* Tema Escuro */
[data-theme="dark"] {
    --text-color: #fff;
    --bg-color: #1a1a1a;
}

/* Layout Components */
.header { /* Cabeçalho fixo */ }
.nav { /* Navegação responsiva */ }
.main { /* Conteúdo principal */ }
.footer { /* Rodapé com player */ }

/* Responsive Design */
@media (max-width: 768px) {
    /* Mobile styles */
}
`

### JavaScript Modules
`javascript
// Theme Management
const themeManager = {
    init() { /* Inicialização do tema */ },
    toggle() { /* Alternância de tema */ },
    save() { /* Persistência no localStorage */ }
};

// Mobile Menu
const mobileMenu = {
    toggle() { /* Toggle do menu mobile */ },
    close() { /* Fechar menu */ }
};

// Radio Player
const radioPlayer = {
    play() { /* Iniciar reprodução */ },
    pause() { /* Pausar reprodução */ },
    setVolume(level) { /* Controle de volume */ }
};

// Header Effects
const headerEffects = {
    addScrollShadow() { /* Sombra no scroll */ }
};
`

## ⚙️ Funcionalidades Detalhadas

### 1. Sistema de Temas
`javascript
// Implementação do Theme Toggle
function toggleTheme() {
    const currentTheme = document.documentElement.getAttribute('data-theme');
    const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
    
    document.documentElement.setAttribute('data-theme', newTheme);
    localStorage.setItem('theme', newTheme);
    
    // Atualizar ícone do botão
    const themeIcon = document.querySelector('#theme-toggle i');
    themeIcon.className = newTheme === 'dark' ? 'fas fa-sun' : 'fas fa-moon';
}

// Carregamento do tema salvo
document.addEventListener('DOMContentLoaded', function() {
    const savedTheme = localStorage.getItem('theme') || 'light';
    document.documentElement.setAttribute('data-theme', savedTheme);
});
`

### 2. Menu Mobile Responsivo
`javascript
// Toggle do menu mobile
function toggleMobileMenu() {
    const mobileMenu = document.querySelector('.mobile-menu');
    const hamburger = document.querySelector('.hamburger');
    
    mobileMenu.classList.toggle('active');
    hamburger.classList.toggle('active');
}

// Fechar menu ao clicar em links
document.querySelectorAll('.mobile-menu a').forEach(link => {
    link.addEventListener('click', () => {
        document.querySelector('.mobile-menu').classList.remove('active');
        document.querySelector('.hamburger').classList.remove('active');
    });
});
`

### 3. Player de Rádio
`javascript
// Controle do player de rádio
let isPlaying = false;
const audio = new Audio('URL_DA_RADIO');

function toggleRadio() {
    const playBtn = document.querySelector('#play-btn');
    
    if (isPlaying) {
        audio.pause();
        playBtn.innerHTML = '<i class="fas fa-play"></i>';
        isPlaying = false;
    } else {
        audio.play();
        playBtn.innerHTML = '<i class="fas fa-pause"></i>';
        isPlaying = true;
    }
}

// Controle de volume
function setVolume(value) {
    audio.volume = value / 100;
}
`

### 4. Integração WhatsApp
`javascript
// WhatsApp Business API Integration
const whatsappConfig = {
    number: "5592995266862",
    apiUrl: "https://api.whatsapp.com/send",
    
    openChat(message = "") {
        const url = ${this.apiUrl}?phone=&text=;
        window.open(url, '_blank');
    }
};
`

## 🔧 Configurações

### Firebase Configuration
`json
// firebase.json
{
  "emulators": {
    "dataconnect": {
      "port": 9399
    }
  },
  "dataconnect": {
    "source": "."
  },
  "hosting": {
    "public": "public",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ]
  }
}
`

### Deploy Configuration
`json
// .firebaserc
{
  "projects": {
    "default": "code-49bf4"
  }
}
`

## 🛠️ Manutenção

### Atualizações de Conteúdo
1. **Textos e Informações**: Editar diretamente nos arquivos HTML
2. **Imagens**: Substituir arquivos na pasta correspondente
3. **Estilos**: Modificar CSS interno em cada página
4. **Funcionalidades**: Atualizar JavaScript interno

### Deploy Process
`ash
# 1. Testar localmente
firebase serve

# 2. Deploy para produção
firebase deploy --only hosting

# 3. Verificar deploy
# Acessar: https://code-49bf4.web.app
`

### Backup e Versionamento
- **Código**: Manter backup local dos arquivos
- **Firebase**: Configurações salvas no console
- **Assets**: Backup das imagens e recursos

## 🔍 Troubleshooting

### Problemas Comuns

#### 1. Menu Mobile não funciona
`javascript
// Verificar se o JavaScript está carregado
console.log('Menu mobile script loaded');

// Verificar eventos
document.querySelector('.hamburger').addEventListener('click', function() {
    console.log('Hamburger clicked');
});
`

#### 2. Tema não persiste
`javascript
// Verificar localStorage
console.log('Tema salvo:', localStorage.getItem('theme'));

// Limpar cache se necessário
localStorage.removeItem('theme');
`

#### 3. Player de rádio não carrega
`javascript
// Verificar URL da rádio
const audio = new Audio();
audio.addEventListener('error', function(e) {
    console.error('Erro no áudio:', e);
});
`

#### 4. WhatsApp não abre
`javascript
// Verificar URL gerada
const testUrl = https://api.whatsapp.com/send?phone=5592995266862&text=Teste;
console.log('URL WhatsApp:', testUrl);
`

### Performance Optimization

#### 1. Otimização de Imagens
- Usar formatos modernos (WebP quando possível)
- Comprimir imagens antes do upload
- Implementar lazy loading se necessário

#### 2. CSS Optimization
- Minificar CSS em produção
- Remover estilos não utilizados
- Usar CSS crítico inline

#### 3. JavaScript Optimization
- Minificar JavaScript
- Usar defer/async quando apropriado
- Implementar service worker para cache

## 📊 Métricas e Monitoramento

### Core Web Vitals
- **LCP (Largest Contentful Paint)**: < 2.5s
- **FID (First Input Delay)**: < 100ms
- **CLS (Cumulative Layout Shift)**: < 0.1

### Ferramentas de Monitoramento
- Google PageSpeed Insights
- Firebase Performance Monitoring
- Google Analytics (se implementado)

## 🔐 Segurança

### Implementações de Segurança
- HTTPS obrigatório (Firebase Hosting)
- Content Security Policy headers
- Sanitização de inputs (se aplicável)
- Validação client-side

### Boas Práticas
- Não expor informações sensíveis no código
- Usar HTTPS para todos os recursos externos
- Implementar rate limiting se necessário

---

**Documentação Técnica v1.0**  
*Última atualização: Janeiro 2025*  
*Igreja Batista Regular de Lagoa Verde*
=======
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
>>>>>>> 4429d0409503364f1e45fb58a31849f0f9cbb6bd
