# Novidades do Editor RX

A versão mais nova fica em cima. O número diz o tipo de mudança: o 1º muda em mudança grande, o 2º quando entra coisa nova e o 3º em correção.

## 2.5.0 — 19/11/2026
Novidades
- O Editor RX se instala sozinho ao abrir, sem perguntas e sem administrador.
- Fica em `%LOCALAPPDATA%\Programs\Editor RX`, com atalho no Iniciar e item em Configurações › Aplicativos para desinstalar.
- Atualiza sozinho pela internet. A versão nova vale quando ele abrir de novo; escondido na bandeja, ele já reabre atualizado.
- Abrir um `Editor RX.exe` de qualquer pasta atualiza o instalado e abre o instalado.
- Inicia com o Windows, só no ícone da bandeja. Para desligar: Ferramentas › Iniciar com o Windows.
- Ferramentas › Procurar atualização confere na hora.
- Novidades no botão ? do topo, junto com a Ajuda: o que mudou em cada versão, com os prints.

  ![Janela de Novidades](Imagens%20das%20novidades/2.5.0-novidades.png)

- Versão nova instalada: o ? fica azul com uma marca e mostra um aviso por 5 segundos. A marca sai quando você abre as Novidades.

  ![Aviso de versão nova embaixo do botão ?](Imagens%20das%20novidades/2.5.0-aviso.png)
- Download da versão mais nova: [Editor-RX.exe no GitHub](https://github.com/davi-ciss/editor-rx/releases/latest/download/Editor-RX.exe).

## 2.4.0 — 19/11/2026
Novidades
- Campo na vertical: texto, coluna ou fórmula lendo de baixo para cima ou de cima para baixo.
- Botão direito no campo › Campo de baixo pra cima na vertical, ou de cima pra baixo.

  ![Menu do botão direito com o texto na vertical](Imagens%20das%20novidades/2.4.0-menu.png)

- Atalho com o campo selecionado: Ctrl+Shift+↑ de baixo pra cima, Ctrl+Shift+↓ de cima pra baixo e Ctrl+Shift+→ volta para a horizontal.

- Ou Propriedades › Fonte › Direção. Os três botões são horizontal, de baixo para cima e de cima para baixo. O que está em uso fica azul.
- O ícone de cada botão mostra as letras do jeito que o texto vai ficar.
- De baixo para cima gira o texto 90° no sentido anti-horário. De cima para baixo gira 90° no sentido horário.

  ![Direção no painel de propriedades e o campo na vertical](Imagens%20das%20novidades/2.4.0-direcao.png)

- A caixa do campo vira alta e estreita sozinha, sem passar do fim da etiqueta.
- O alinhamento esquerda começa onde a leitura começa: embaixo no de baixo para cima.
- A pré-visualização já mostra o campo girado.

  ![Pré-visualização com o campo na vertical](Imagens%20das%20novidades/2.4.0-preview.png)

- Pelo Claude: ferramenta `rex_objetos_girar`.

## 2.3.2 — 18/11/2026
Correções
- IA que carrega o MCP ao iniciar, como o Codex, não abre mais o Editor RX sozinho. Ele só abre quando a IA usa uma ferramenta.
- Várias sessões da IA ao mesmo tempo não abrem várias janelas.
- O Editor RX aberto pela IA fica só no ícone da bandeja. A janela aparece no clique do ícone.
- Para abrir já com a janela: menu do ícone › desmarcar "Abrir só o ícone, sem a janela".

## 2.3.1 — 17/11/2026
Correções
- Erro de conexão com o banco agora diz o servidor e a porta, com o código do DB2 no fim.
- O nome do banco não vem mais com espaços sobrando.
- A mensagem de erro da tela de conexão rola e fica à vista em janela baixa.

## 2.3.0 — 06/11/2026
Novidades
- Código de barras em etiqueta: botão Código de barras na barra do layout e no menu de contexto.
- As fontes de código de barras do CISSPoder vêm dentro do `.exe`: EAN-13, LBPremium, Code 128, Code 39 e 2 de 5.
- O código é montado do jeito que o CISSPoder imprime, e o layout e a pré-visualização mostram as barras.
- Aviso quando a fonte não está instalada no Windows. Sem ela, o CISSPoder daquele computador não imprime.
- Pelo Claude: ferramentas `rex_codbar_fontes` e `rex_codbar_inserir`.

## 2.2.2 — 05/11/2026
Correções
- "Abrir com" do Windows acha o `.exe` pelo nome com a versão.
- Ícone aparece certo no Explorer e na barra de tarefas.

## 2.2.1 — 05/11/2026
Correções
- Descrição do relatório com várias linhas aparece separada por linha no CISSPoder. Antes ficava tudo junto.

## 2.2.0 — 05/11/2026
Novidades
- O X da janela pergunta se fica em segundo plano ou se fecha. "Não perguntar de novo" grava a escolha, e Ferramentas › Ao fechar a janela muda depois.
- Em segundo plano fica só o ícone na bandeja. Abrir o `.exe` de novo traz a mesma janela.
- O nome do arquivo no topo abre o caminho inteiro, com Copiar e Abrir no Explorer.
- Com a IA ligada, aparece "IA" no topo.

## 2.1.0 — 05/11/2026
Novidades
- O Claude usa a janela do Editor RX que já está aberta. Ele vê o documento da tela, inclusive o que não foi salvo, e a conexão com o banco.
- Quando a sessão do Claude termina, ele só se desliga e a janela continua aberta.
- A versão vai no nome do `.exe`. Ao abrir o novo pelo Explorer, ele corrige sozinho o caminho do MCP no Claude.
