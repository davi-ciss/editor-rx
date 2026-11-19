# Configurar para uso com IA

O Editor RX também é um servidor MCP. Com ele, o Claude Code abre, cria, confere e visualiza `.REX`, `.EFG` e `.EFP` usando o próprio editor, e você acompanha tudo na janela.

## O que precisa
- Claude Code, no app desktop ou no terminal.
- O Editor RX instalado e ativado neste computador.
- Para conectar no banco: o driver IBM DB2 ODBC, o mesmo do CISSPoder.

## Jeito rápido: pedir para o Claude configurar
Cole o texto abaixo numa sessão do Claude Code.

```text
Configure o MCP do Editor RX neste computador e confira se funciona. Fale comigo em português. Siga os passos na ordem e me avise o resultado de cada um.

O app e o MCP são um arquivo só. Ele se instala sozinho ao abrir, em %LOCALAPPDATA%\Programs\Editor RX\Editor RX.exe, e se atualiza sozinho. Download: https://github.com/davi-ciss/editor-rx/releases/latest/download/Editor-RX.exe

1. Instalação. Se %LOCALAPPDATA%\Programs\Editor RX\Editor RX.exe não existir, peça para eu baixar o .exe e abrir com dois cliques no Explorer. Não abra você: o app aberto pelo Claude pode gravar a instalação e a ativação numa cópia separada do Windows.
2. Ativação. Se aparecer a tela de ativação, eu mando o código para quem fornece a chave e colo a chave. Espere eu confirmar que o app abriu.
3. Banco. No app aberto pelo Explorer, peça para eu criar o perfil de conexão: botão do banco, DSN ou servidor, porta, banco e usuário, marcar "Lembrar a senha" e conectar. Nunca me peça a senha e nunca grave senha em arquivo.
4. Registro. Rode pelo PowerShell: & "$env:LOCALAPPDATA\Programs\Editor RX\Editor RX.exe" --registrar-mcp e mostre a saída. Ele grava o servidor editor-rx no ~/.claude.json e guarda uma cópia do arquivo anterior.
5. Regras. Pergunte se eu quero gravar estas regras no meu ~/.claude/CLAUDE.md, e só grave se eu disser sim:
   - Editor RX: ao criar ou alterar relatório, conectar num banco antes, com rex_banco_perfis e rex_banco_conectar. Dados fictícios só em último caso, avisando.
   - Banco de cliente só depois de eu confirmar qual. Nunca pedir nem gravar senha.
   - Filtros do relatório vêm do banco, com rex_banco_filtros_sistema.
6. Teste. Peça para eu abrir uma sessão nova do Claude Code e, nela, pedir: "use rex_app_estado e rex_banco_perfis". O certo é aparecer o modo "fora do contêiner (WMI)" e o meu perfil com senhaGuardada: true.

Se algum passo falhar, mostre o erro e pare. Não tente contornar.
```

## Jeito manual
1. Baixe o [Editor-RX.exe](https://github.com/davi-ciss/editor-rx/releases/latest/download/Editor-RX.exe) e abra com dois cliques. Ele se instala sozinho e pede a ativação na primeira vez.
2. No Editor RX, crie o perfil do banco: botão do banco, escolha o DSN ou informe servidor, porta, banco e usuário, marque "Lembrar a senha" e conecte.
3. No PowerShell, registre o MCP:

   ```powershell
   & "$env:LOCALAPPDATA\Programs\Editor RX\Editor RX.exe" --registrar-mcp
   ```

4. Abra uma sessão nova do Claude Code. As ferramentas começam com `rex_` e os comandos `/rx-criar`, `/rx-atualizar` e `/rx-conferir` aparecem no menu `/`.

Para tirar: `& "$env:LOCALAPPDATA\Programs\Editor RX\Editor RX.exe" --tirar-mcp`.

## Como funciona
- A senha do banco fica criptografada no seu usuário do Windows. O MCP usa o perfil e nunca recebe a senha. Por isso o perfil é criado no app aberto pelo Explorer, não pelo Claude.
- A conexão do editor é só leitura. A única gravação é o Importar no banco, que primeiro mostra o que muda e só grava depois do seu OK.
- Com o Editor RX aberto, o Claude usa essa mesma janela e vê o que está na tela, inclusive o que ainda não foi salvo. Aparece "IA" no topo enquanto ele estiver ligado.
- Sem o Editor RX aberto, o Claude abre um separado, só com o ícone na bandeja, quando usa a primeira ferramenta. Ele fecha junto com a sessão.
- O Editor RX se atualiza sozinho e o registro do MCP continua valendo. Depois de uma atualização, abra uma sessão nova do Claude Code para pegar as ferramentas novas.

## Exemplos de pedido
- "cria um REX na horizontal com os títulos do contas a receber e o nome fantasia do cliente"
- "confere este .REX e diz o que está errado"
- "põe a coluna de vencimento no relatório 151 e filtro por empresa"

Antes de montar, o Claude pergunta colunas, filtros, ordenação, totais, orientação, banco, ID e pasta. Ele sugere o que pode ser útil, mas só inclui se você aceitar.
