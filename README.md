# Gerador de Etiquetas Térmicas (12cm x 4.5cm)

Aplicação web em arquivo único para geração, pré-visualização em tempo real e impressão de etiquetas térmicas em bobinas de 10cm x 15cm. O layout é otimizado para equipamentos corporativos e identificação patrimonial.

---

## 📁 Estrutura de Arquivos

```text
Etiquetas_Notebook/
├── index.html                                        # Aplicação completa (HTML, CSS e JS)
├── 6a7ee28c-f14c-4c40-9b54-b2963b01547d.jfif        # Imagem/logo padrão para upload
└── README.md                                         # Documentação do projeto
```

---

## 🚀 Funcionalidades

- **Padronização em Maiúsculas:** Conversão automática de todos os campos digitados ou colados para letras maiúsculas em tempo real.
- **Título Inteligente:** Concatena automaticamente `LOCAL / SETOR` e `CARGO / SUB-IDENTIFICAÇÃO` com separador ` - ` (ex: `ALMOXARIFADO - TI - ATIVOS`) apenas quando ambos estiverem preenchidos.
- **Responsáveis (Até 3 Linhas):** Campo multilinha com trava estrita contra criação ou colagem de 4 ou mais linhas, mantendo o formato vertical na etiqueta.
- **Serial Alfanumérico Estrito:** Limite exato de 7 caracteres alfanuméricos (`[A-Z0-9]`), bloqueando caracteres especiais ou espaços.
- **QR Code Puro:** Geração instantânea do QR Code contendo estritamente o valor do serial (sem prefixos ou URLs externas).
- **Upload e Remoção de Logotipo:** Suporte a arquivos de imagem locais (PNG, JPG, JFIF, SVG) com pré-visualização, status de confirmação e botão de remoção limpa.
- **Modos de Visualização:** Alternância entre visão de papel real rotacionado a 90° na bobina e modo horizontal de conferência rápida.
- **Calibragem Física:** Controles para ajuste fino das margens superior (`mm`) e lateral (`cm`) da impressora.

---

## 📐 Especificações Técnicas da Etiqueta

| Propriedade | Valor / Regra |
| :--- | :--- |
| **Dimensões Reais da Etiqueta** | 12,0 cm (comprimento) x 4,5 cm (altura) |
| **Dimensões do Papel / Bobina** | 10,0 cm x 15,0 cm (`@page { size: 10cm 15cm; margin: 0; }`) |
| **Orientação no Papel** | Rotacionada em 90° (`transform: rotate(90deg)`) |
| **Posicionamento Padrão** | `top: 3mm` \| `left: 6cm` |
| **Tamanho do QR Code** | 70px x 70px |
| **Tamanho da Logo** | 40px x 40px |
| **Família Tipográfica** | Arial / Arial Black |

---

## 🖨️ Instruções para Impressão

Para garantir a escala correta e sem deslocamentos na cabeça de impressão térmica:

1. Abra o arquivo `index.html` em qualquer navegador moderno (Google Chrome, Microsoft Edge ou Firefox).
2. Preencha os campos desejados e faça o upload da logo (`6a7ee28c-f14c-4c40-9b54-b2963b01547d.jfif`) localizada na pasta.
3. Clique no botão **Imprimir Etiqueta** (ou utilize o atalho `Ctrl + P`).
4. Na tela de diálogo de impressão do navegador, defina:
   - **Destino:** Sua impressora térmica de bobina.
   - **Tamanho do papel:** `100 x 150 mm` (ou `10 x 15 cm`).
   - **Margens:** `Nenhuma` (None).
   - **Escala:** `Padrão` (100%).
   - **Opções:** Desmarque **"Cabeçalhos e rodapés"**.

---

## 🛠️️ Tecnologias Utilizadas

- **HTML5 & CSS3 nativo** (estilização impressa com regras `@media print`)
- **[Tailwind CSS (CDN)](https://tailwindcss.com/)** (interface do painel de controle)
- **[QRCode.js](https://davidshimjs.github.io/qrcodejs/)** (renderização do código 2D em elemento canvas/img)
- **[Lucide Icons](https://lucide.dev/)** (iconografia do formulário e interface)
