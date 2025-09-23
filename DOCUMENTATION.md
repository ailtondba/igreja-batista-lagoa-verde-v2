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
