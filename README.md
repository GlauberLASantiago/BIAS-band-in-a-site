# 🎵 BIAS: Band-in-a-Site

Uma aplicação web interativa para montar e ouvir sequências de acordes de jazz/swing diretamente no navegador, sem necessidade de instalação.

<img width="1174" height="865" alt="image" src="https://github.com/user-attachments/assets/c21a554b-d1c4-47b7-bccf-c2aa9afe267a" />


Desenvolvida pelo professor **Glauber Santiago** — DAC/UFSCar.

---

## ✨ Funcionalidades

- **Montagem de acordes:** Selecione a nota fundamental (C, C#, D, ..., B) e o tipo de acorde (maj7, 9, 7b9, m7, m7b5, dim7) para adicionar à sequência.
- **Reprodução em tempo real:** Toque a sequência montada com áudio gerado a partir de samples reais de swing (130 BPM nativo).
- **Controle de BPM:** Ajuste o andamento livremente entre 60 e 240 BPM.
- **Efeito de Reverb:** Controle a quantidade de reverberação via slider.
- **Duração dos acordes:** Escolha entre compasso inteiro (4 tempos) ou metade (2 tempos).
- **Substituição de acordes:** Clique num acorde da sequência para substituí-lo.
- **Tema claro/escuro:** Alternância de tema com preferência salva no `localStorage`.

## 📤 Exportação

A ferramenta **Dados & Exportação** oferece os seguintes formatos:

| Formato | Descrição |
|---|---|
| `.txt` (Projeto) | Salva e carrega a sequência para continuar editando |
| `.wav` (Áudio) | Exporta a trilha processada em alta qualidade |
| `.png` (Imagem) | Folha de acordes estruturada com marcação de compassos |
| `.md` (Tabela) | Tabela Markdown da sequência |
| `.musicxml` | Compatível com MuseScore, Finale, Sibelius e Dorico |
| `.txt` (BIAB) | String para Band in a Box ou sequenciadores de texto |

---

## 🚀 Como usar

1. Abra o arquivo `index.html` diretamente no navegador **ou** acesse a versão publicada via GitHub Pages.
2. Selecione uma **nota fundamental** na barra de Fundamental.
3. Clique em um **tipo de acorde** (maj7, 9, etc.) para adicioná-lo à sequência.
4. Pressione **Tocar** para ouvir a sequência.
5. Use o botão **Dados & Exportação** para salvar ou exportar seu trabalho.

> **Nota sobre a cifragem:** `9` representa um acorde com sétima menor e nona; `dim7` é uma tétrade diminuta.

---

## 🛠️ Tecnologias

- **HTML5** — estrutura única em `index.html` (sem dependências de build)
- **[Tailwind CSS](https://tailwindcss.com/)** — via CDN
- **[Font Awesome 6](https://fontawesome.com/)** — ícones
- **Web Audio API** — síntese de áudio e efeito de reverb no navegador
- **Canvas API** — geração da imagem exportável

---

## 📁 Estrutura

```
BIAS-band-in-a-site/
└── index.html   # Aplicação completa (HTML + CSS + JavaScript)
```

---

## 👤 Autor

**Glauber Santiago**
- 🌐 [servidores.ufscar.br/glauber/](https://servidores.ufscar.br/glauber/)
- 🌐 [sites.google.com/view/glauberia](https://sites.google.com/view/glauberia)
- Departamento de Artes e Comunicação (DAC) — UFSCar

---

## 📄 Licença

Este projeto é de autoria do professor Glauber Santiago. Consulte o autor para informações sobre uso e distribuição.
