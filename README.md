# 🛸 Missão de Desenvolvimento: Painel de Controle da Nave "Code-1"

> **Agência Espacial:** Space Program  
> **Ano:** 2088  
> **Nível:** Introdução a Eventos, Funções e Estruturas Condicionais em JavaScript  

---

## 📜 A História

O ano é **2088**. Vocês foram contratados pela agência espacial **Space Program** para programar o computador de bordo da nave espacial **Code-1**. A nave está em uma missão crucial de exploração e a tripulação precisa de um painel interativo simples para acionar comandos de emergência rapidamente.

Como o sistema principal de telas avançadas da nave sofreu uma avaria, a interface emergencial precisa rodar com botões de acionamento imediato (`onclick`) que conversam com o piloto por meio de caixas de diálogo e mensagens instantâneas (`prompt` e `alert`).

---

## 📋 Arquitetura do Painel de Controle

O painel deve ser entregue com a seguinte estrutura visual e 4 botões de controle funcionais:

```text
┌────────────────────────────────────────────────────────┐
│           🛸 PAINEL DE CONTROLE - CODE-1               │
│                                                        │
│  [ 🟢 Status da Nave ]     [ 🟡 Iniciar Propulsores ] │
│                                                        │
│  [ 🔴 Radar de Ameaças ]    [ 🟣 Diário de Bordo ]    │
└────────────────────────────────────────────────────────┘
```

---

## 📂 Estrutura do Projeto

Cada aluno (ou dupla) deverá criar e integrar 3 arquivos no repositório:

- `index.html` — Estrutura dos botões e gatilhos de eventos.
- `style.css` — Estilização futurista do painel espacial.
- `script.js` — Lógica dos comandos e funções de bordo.

---

## 🛠️ Especificação Técnica das Funções (`script.js`)

### 1. 🟢 Status da Nave
- **Gatilho HTML:** `onclick="checarStatus()"`
- **Lógica:** Função sem entrada de dados. Dispara um `alert()` informando o estado geral da nave.
- **Exemplo de saída:**
  ```javascript
  alert("✅ Nível de Oxigênio: 100% | Combustível: Estável | Escudos: Ativos");
  ```

### 2. 🟡 Iniciar Propulsores
- **Gatilho HTML:** `onclick="calcularPropulsoes()"`
- **Lógica:** Solicita a velocidade desejada via `prompt()`, converte o texto para número, calcula o consumo de energia ($\text{consumo} = \text{velocidade} \times 2.5$) e exibe o resultado via `alert()`.
- **Exemplo de saída:**
  ```javascript
  alert("⚡ Para viajar a " + vel + " km/s, a nave consumirá " + energia + " MW de energia.");
  ```

### 3. 🔴 Radar de Ameaças
- **Gatilho HTML:** `onclick="verificarAmeaca()"`
- **Lógica:** Solicita a distância do objeto mais próximo em km via `prompt()`. Utiliza a estrutura condicional `if / else`:
  - **Se a distância for menor que 1000 km:** `alert("🚨 ALERTA CRÍTICO: Objeto muito próximo! Ativar escudos!");`
  - **Caso contrário:** `alert("🟢 Radar Limpo: Nenhum risco detectado no setor.");`

### 4. 🟣 Diário de Bordo
- **Gatilho HTML:** `onclick="registrarDiario()"`
- **Lógica:** Realiza dois chamados `prompt()` sequenciais (Nome do Astronauta e Relato da Missão). Concatena as informações e exibe o relatório oficial via `alert()`.
- **Exemplo de saída:**
  ```javascript
  alert("📝 REGISTRO OFICIAL\nAstronauta: " + nome + "\nRelato: " + relato);
  ```

---

## 🎨 Guia de Estilização CSS — Painel Futurista

Siga a especificação abaixo no arquivo `style.css` para criar uma interface visual no estilo "espaço profundo".

### 📐 1. Layout e Fundo da Página (`body`)
- **Cor de Fundo (`background-color`):** `#0b0d17` (Azul escuro espacial)
- **Tipografia (`font-family`):** `Arial, Helvetica, sans-serif`
- **Alinhamento Centralizado:** Use Flexbox (`display: flex; justify-content: center; align-items: center;`)
- **Altura Total (`height`):** `100vh`
- **Margem (`margin`):** `0`

### 📦 2. O Card do Painel (`.painel-nave`)
- **Largura (`width`):** `320px`
- **Cor de Fundo (`background-color`):** `#15192b`
- **Espaçamento Interno (`padding`):** `30px`
- **Borda (`border`):** `2px solid #2a3254`
- **Cantos Arredondados (`border-radius`):** `12px`
- **Sombra Neon (`box-shadow`):** `0 0 20px rgba(0, 150, 255, 0.2)`
- **Alinhamento de Texto (`text-align`):** `center`

### 🔤 3. Títulos e Textos
- **Título (`h1`):**
  - **Cor (`color`):** `#00d2ff` (Ciano brilhante)
  - **Remover Margem Superior (`margin-top`):** `0`
  - **Tamanho da Fonte (`font-size`):** `22px`
- **Subtítulo (`p`):**
  - **Cor (`color`):** `#a0aabf` (Prateado)
  - **Tamanho da Fonte (`font-size`):** `14px`
  - **Margem Inferior (`margin-bottom`):** `25px`

### 🔘 4. Estilo Base dos Botões (`.btn`)
- **Largura (`width`):** `100%`
- **Espaçamento Interno (`padding`):** `12px`
- **Espaçamento entre Botões (`margin-top`):** `10px`
- **Fonte (`font-weight`):** `bold` | **Tamanho (`font-size`):** `15px`
- **Cor do Texto (`color`):** `#ffffff`
- **Borda (`border`):** `none` | **Raio da Borda (`border-radius`):** `6px`
- **Cursor (`cursor`):** `pointer`

### 🎨 5. Cores Específicas por Classe de Botão

| Botão | Classe CSS | Cor Hexadecimal | Significado no Painel |
| :--- | :--- | :--- | :--- |
| 🟢 **Status da Nave** | `.btn-status` | `#28a745` | Verde (Sistemas seguros) |
| 🟡 **Iniciar Propulsores** | `.btn-propulsor` | `#ffc107` | Amarelo (Atenção / Energia) |
| 🔴 **Radar de Ameaças** | `.btn-radar` | `#dc3545` | Vermelho (Alerta de perigo) |
| 🟣 **Diário de Bordo** | `.btn-diario` | `#6f42c1` | Roxo (Relatório oficial) |

###⚡ 6. Efeito de Interatividade (:hover)
- Para dar sensação de que o botão é um interruptor de verdade:

CSS
```css
.btn:hover {
  opacity: 0.85; /* Suaviza a cor quando o mouse passa por cima */
  transform: scale(1.02); /* (Opcional) Aumenta levemente o botão ao passar o mouse */
}
```
---

## 📥 Guia de Entrega

1. Crie uma pasta para o projeto no seu computador.
2. Codifique os arquivos `index.html`, `style.css` e `script.js`.
3. Teste todos os 4 botões no seu navegador.

🚀 *Que a força do código esteja com você, astronauta!*
