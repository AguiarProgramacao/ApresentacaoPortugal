# 📄 Gerador de PDF - Apresentação Nacionalidade Portuguesa

Este projeto gera uma **apresentação em PDF** para propostas de reconhecimento da nacionalidade portuguesa, utilizando **[jsPDF](https://github.com/parallax/jsPDF)**.  
Os valores inseridos em **euros (€)** são automaticamente convertidos para **reais (R$)** com base na **cotação atual do euro**.

---

## 🚀 Funcionalidades

- Geração automática de um **PDF em formato paisagem (1920x1080)**.  
- Conversão de valores em **€ para R$** usando cotação atual.  
- Inserção de imagens de fundo (`/assets/img-1.jpg`, `/assets/img-2.jpg`, etc.).  
- Impressão de **honorários, taxa e total** no PDF.  
- Download automático do arquivo `Apresentação-Reunião.pdf`.

---

## 🛠️ Tecnologias Utilizadas

- **JavaScript (ES6+)**
- **jsPDF**
- **HTML/CSS**
- Função assíncrona para **obter cotação do Euro** (`obterCotacaoEuro()`).

---

## 📂 Estrutura do Projeto

```bash
.
├── assets/
│   ├── img-1.jpg
│   ├── img-2.jpg
│   ├── ...
│   └── img-14.jpg
├── index.html
├── script.js   # Função gerarPDF()
└── README.md
⚙️ Como Usar
Instale o jsPDF no seu projeto:

html
Copiar código
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
Certifique-se de que você possui:

Os inputs/elementos com os IDs:

html
Copiar código
<input id="honorario" type="number" value="800">
<input id="taxa" type="number" value="175">
As imagens de fundo em /assets/img-1.jpg até /assets/img-14.jpg.

Implemente a função obterCotacaoEuro() para buscar a cotação atual (exemplo usando uma API):

js
Copiar código
async function obterCotacaoEuro() {
  try {
    const res = await fetch("https://api.exchangerate.host/latest?base=EUR&symbols=BRL");
    const data = await res.json();
    return data.rates.BRL;
  } catch (err) {
    console.error("Erro ao obter cotação:", err);
    return null;
  }
}
Chame a função gerarPDF() no seu frontend:

html
Copiar código
<button onclick="gerarPDF()">Gerar PDF</button>
📊 Exemplo de Saída
Cotação do euro atual: R$ 6,34

Honorários: €800 → R$ 5.072,00

Taxa: €175 → R$ 1.109,50

Total: €975 → R$ 6.181,50

📥 Download Automático
Ao clicar no botão Gerar PDF, o arquivo Apresentação-Reunião.pdf será automaticamente baixado no navegador.

📌 Observações
A cotação é sempre buscada no momento da geração do PDF.

Os valores exibidos podem variar de acordo com a cotação do euro.

As imagens devem estar na pasta /assets com os nomes img-1.jpg até img-14.jpg.

📄 Licença
Este projeto é de uso privado e voltado para propostas comerciais.
