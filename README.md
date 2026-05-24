# 🎹 BIAS: Band-in-a-Site

O **BIAS (Band-in-a-Site)** é uma aplicação web interativa de página única (SPA) projetada para a montagem, edição, visualização e exportação de sequências harmônicas (cifras) com suporte a acompanhamento de áudio. Desenvolvido para fins didáticos pelo professor **Glauber Santiago** (DAC/UFSCar), o aplicativo permite que estudantes e educadores criem grades de acordes rapidamente e gerem bases em áudio de alta qualidade ou compressão otimizada.

Tudo é executado diretamente no navegador (Client-Side), sem a necessidade de servidores ou bancos de dados adicionais.

---

## 🚀 Principais Funcionalidades

### 🎼 Edição e Escrita de Acordes
* **Teclado de Piano Virtual Interativo**: Integrado diretamente no app para seleção rápida da fundamental. Conta com comportamento enarmônico inteligente nas teclas pretas (clicar duas vezes na mesma tecla alterna o estado entre sustenido e bemol, atualizando toda a interface de forma contextualizada).
* **Grade de Compassos Flexível**: Inicializa por padrão com 32 compassos (grade de 4 em 4) de 4 tempos (4T). Permite ajustar dinamicamente o tamanho total da música de 1 a 128 compassos.
* **Divisão e Fusão Dinâmica (Split & Merge)**: Dando um **duplo clique** em qualquer bloco de acorde de 4 tempos, ele se divide ao meio em dois slots de 2 tempos (2T). Um novo duplo clique une-os de volta, preservando a harmonia.
* **Reconhecimento de Digitação Direta**: Basta clicar em um slot e digitar as cifras no teclado físico (ex: digitar `C`, `Eb`, `F#m7`). O sistema possui um buffer inteligente de entrada com cursor ativo e autocompleta automaticamente assim que a qualidade do acorde é reconhecida, avançando para o próximo compasso.

### 📋 Usabilidade, Histórico e Área de Transferência
* **Sincronização de Foco Automática**: Ao selecionar um acorde já montado na sequência, a fundamental selecionada no teclado de piano virtual é atualizada automaticamente para a mesma do acorde em foco, permitindo alterar a qualidade do acorde com facilidade (ex: transformar `G9` em `Gm7` clicando apenas na qualidade).
* **Histórico de Alterações (Undo/Redo)**: Atalhos universais integrados para desfazer (`Ctrl+Z`) e refazer (`Ctrl+Y`) ações de inserção, alteração, remoção e colagem de acordes, oferecendo controle total de edição.
* **Seleção Múltipla com Mouse**:
  * **Clique Simples**: Seleciona e ativa um slot para edição harmônica.
  * **Shift + Clique**: Seleciona um intervalo contínuo de compassos.
  * **Ctrl + Clique** (ou Cmd): Seleciona ou remove múltiplos compassos não contíguos de forma independente.
* **Copiar & Colar Integrado**: Suporta comandos do teclado (`Ctrl+C` e `Ctrl+V`) ou botões na interface para duplicar compassos selecionados e colá-los a partir de um slot de destino.

### 🔊 Visualização de Som e Acompanhamento
* **Visor de Notas Interativo (Teoria Musical)**: Exibe as notas do acorde em foco em português no rodapé. Utiliza enarmonia teórica exata de graus musicais (ex: `mi#` no C#9, `sibb` no Cdim7, `fáb` no Dbm7). As notas individuais são **clicáveis e audíveis**, reproduzindo tons sintetizados em escala estritamente ascendente (do grave para o agudo).
* **Controles de Reprodução Direcionados**:
  * **Tocar do Início**: Executa a partitura de áudio completa desde o compasso 1.
  * **Tocar do Selecionado**: Inicia a reprodução a partir do compasso/acorde atualmente focado na sequência.
* **Sintetizador de Preview de Piano**: Ao clicar em uma nota fundamental ou em um tipo de qualidade (sétimas, nonas, etc.), o sistema sintetiza na hora um preview de áudio suave utilizando a **Web Audio API** com ondas senoidais (`sine`) puras e harmônicos integrados para emular a ressonância de cordas de piano, associados a um envelope percussivo de decaimento natural.
* **Reprodutor e Consolidador**: Permite tocar a sequência completa utilizando áudios reais de acompanhamento em ritmo de *Swing* (130 BPM nativos) com controle de pitch adaptativo (BPM de 60 a 240) e efeito de **Reverb espacial** dinâmico.


### 💾 Exportações Avançadas
O menu **Dados & Exportação** oferece múltiplos formatos profissionais:
1. **Projeto (.txt)**: Salva todo o progresso localmente em formato JSON para importação futura.
2. **Código para Moodle (HTML)**: Gera o código HTML completo embutindo o áudio em formato Base64 para ser colado em ambientes virtuais de aprendizagem, com uma visualização de partitura elegante que inclui barras de compasso e cifras.
   * *Opção MP3 (Mais Leve)*: Utiliza o encoder LameJS para comprimir o áudio e otimizar o carregamento no Moodle.
   * *Opção WAV (Alta Qualidade)*: Exporta áudio não comprimido.
3. **Áudio Independente (.wav)**: Baixe o arquivo de áudio renderizado da sua trilha para uso em outros reprodutores.
4. **Exportação de Imagem (.png)**: Gera uma folha de partitura visual estruturada, contendo a numeração dos compassos (incluindo subdivisões de splits, ex: `1.3`) e cifras centralizadas.
5. **Tabela Markdown (.md)**: Transforma a harmonia em formato tabular compatível com GitHub e editores de markdown.
6. **MusicXML 3.1**: Exporta as cifras e pausas estruturadas, permitindo a importação direta no MuseScore, Sibelius, Finale e outras ferramentas de notação.
7. **Band-in-a-Box (BIAB)**: Gera a string de cifras estruturada com separadores de compasso e tempos no formato interpretado pelo software Band-in-a-Box.

---

## 🛠️ Tecnologias Utilizadas

* **Estrutura**: HTML5 semântico.
* **Estilização**: [Tailwind CSS](https://tailwindcss.com/) (carregado via CDN para portabilidade) com suporte nativo a **Dark Mode** e paleta de cores customizada.
* **Lógica**: JavaScript Vanilla (ES6+) assíncrono.
* **Áudio**: 
  * [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) (Síntese subtrativa, convolução de reverb, e consolidação off-line em `OfflineAudioContext`).
  * [LameJS](https://github.com/zhuker/lamejs) (Conversão em tempo real do buffer decodificado para MP3 comprimido no cliente).
* **Ícones**: Font Awesome 6.

---

## 💻 Como Executar o Projeto

Como o projeto é construído em Vanilla JS sem etapas de compilação obrigatórias, você pode executá-lo de forma simples:

1. Clone o repositório ou baixe o código fonte:
   ```bash
   git clone https://github.com/seu-usuario/bias-band-in-a-site.git
   ```
2. Abra o arquivo `index.html` diretamente em seu navegador web (dê dois cliques no arquivo ou utilize a extensão *Live Server* no VS Code).

Pronto! A aplicação estará funcionando instantaneamente com todas as suas ferramentas e sintetizadores de som.

---

## 🎨 Temas e Interface
A interface foi otimizada para ocupar **100% da largura da tela**, aproveitando ao máximo o espaço de trabalho em desktops sem distorção e com responsividade total para tablets e celulares. Além disso, conta com um botão de alternância de tema no cabeçalho (**Modo Escuro / Modo Claro**), salvando a preferência do usuário no `localStorage`.

---

## ✉️ Contato e Créditos

Desenvolvido pelo professor **Glauber Santiago**
* Departamento de Artes e Comunicação (DAC) — Universidade Federal de São Carlos (**UFSCar**)
* Portfólio acadêmico: [servidores.ufscar.br/glauber/](https://servidores.ufscar.br/glauber/)
* Site Glauberian: [sites.google.com/view/glauberia](https://sites.google.com/view/glauberia)
