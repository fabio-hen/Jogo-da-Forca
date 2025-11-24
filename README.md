# 🪢 Jogo da Forca em Python

Este é um jogo da forca em Python que utiliza palavras reais obtidas automaticamente a partir da API do **Dicionário Aberto**. O objetivo é adivinhar a palavra sorteada antes que todas as tentativas se esgotem.

## 🎮 Como funciona

* O jogo consulta a API do Dicionário Aberto e busca **10 palavras aleatórias**, filtrando apenas palavras:

  * sem acentos
  * entre 4 e 10 caracteres
  * compostas apenas por letras
* Uma palavra da lista é sorteada para a partida.
* O jogador tem **6 tentativas** para adivinhar a palavra.
* A cada rodada:

  * É exibida a palavra oculta com `*`.
  * O jogador informa uma letra.
  * Caso já tenha tentado aquela letra, o jogo avisa.
  * Se a letra existir na palavra, ela é revelada no local correto.
  * Caso contrário, o jogador perde uma tentativa.
* A partida termina quando:

  * O jogador descobre todas as letras (**vitória**), ou
  * As tentativas chegam a zero (**derrota**).

## 🧠 Funcionalidades principais

### ✔️ Coleta de palavras reais

O jogo usa o endpoint:

```
https://api.dicionario-aberto.net/random
```

Cada palavra recebida é normalizada usando `unicodedata` para remover acentos, garantindo entradas limpas.

### ✔️ Estrutura do jogo

* Contagem de tentativas
* Registro de letras já tentadas
* Atualização dinâmica da palavra oculta
* Controle de fluxo para vitória ou derrota

## 📦 Dependências

Certifique-se de instalar a biblioteca **requests**:

```bash
pip install requests
```

Todas as demais dependências fazem parte da biblioteca padrão do Python.

## ▶️ Como executar

1. Salve o código em um arquivo, por exemplo:

   ```
   forca.py
   ```
2. Execute no terminal:

   ```bash
   python forca.py
   ```

## 📝 Observações

* Caso a API esteja fora do ar, o código tentará novamente até conseguir montar a lista de palavras.
* Você pode ajustar o número de tentativas, tamanho das palavras ou regras de filtragem.

## 🚀 Melhorias futuras (sugestões)

* Interface gráfica (Tkinter ou PyQt)
* Suporte a temas (animais, objetos, cidades, etc.)
* Exibir desenho da forca a cada erro
* Salvar histórico de partidas

---

