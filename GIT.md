COMANDOS GERAIS GIT

1 - git-help - Exibe informações de ajuda sobre o Git

2 - git init - Cria um repositório do Git a partir do diretório que está

3 - git-clean - Remove arquivos não rastreados da árvore de trabalho

4 - git-log - Mostra logs de confirmação

5 - git-status - Mostra o status da árvore de trabalho

6 - git ls - Mostra informações sobre arquivos no índice e na árvore de trabalho








COMANDO RESET

git-reset - Redefine o HEAD atual para o estado especificado


git reset [<modo>] [<commit>]
Esse formulário redefine o cabeçalho de ramificação atual para <commit> e
possivelmente atualiza o índice (redefinindo-o para a árvore de <commit> ) e
a árvore de trabalho, dependendo de <mode> .
Se <mode> for omitido, o padrão será --mixed . O <mode> deve ser um dos seguintes:

--soft
Não toca no arquivo de índice nem na árvore de trabalho (mas redefine o cabeçalho para <commit>,
 assim como todos os modos).

--mixed
Redefine o índice, mas não a árvore de trabalho (ou seja, os arquivos alterados são preservados,
 mas não marcados para confirmação) e relata o que não foi atualizado. Esta é a ação padrão.


--hard
Redefine o índice e a árvore de trabalho. Quaisquer alterações nos arquivos
rastreados na árvore de trabalho desde que <commit> sejam descartadas.

--merge
Redefine o índice e atualiza os arquivos na árvore de trabalho que são
 diferentes entre <commit> e HEAD , mas mantém aqueles que são diferentes entre o índice e a
 árvore de trabalho (ou seja, que apresentam alterações que não foram adicionadas).

--keep
Redefine as entradas de índice e atualiza os arquivos na árvore de trabalho que são
diferentes entre <commit> e HEAD.



COMANDO REMOTE

git-remote - Gerenciar conjunto de repositórios rastreados

OPÇÕES
-v
--verbose
Seja um pouco mais detalhado e mostre o URL remotA após o nome. NOTA: Isso deve ser colocado entre o remote e o subcommand.



COMANDO FETCH

git-fetch - Faz o download de objetos e referências de outro repositório

OPÇÕES
--all
Busque todos os controles remotos.

-a
--append
Anexe nomes de referência e nomes de objetos de referências buscadas ao conteúdo existente de .git/FETCH_HEAD .

--shallow-since = <data>
Aprofundar ou abreviar o histórico de um repositório superficial para incluir
todos os commit alcançáveis Ã¢Â€Â‹Ã¢Â€Â‹após <data>.

--shallow-exclude = <revisão>
Aprofundar ou diminuir o histórico de um repositório superficial para excluir
confirmações alcançáveis Ã¢Â€Â‹Ã¢Â€Â‹de uma ramificação ou tag remota especificada.

--unshallow
Se o repositório de origem estiver completo, converta um repositório raso em um completo,
 removendo todas as limitações impostas por repositórios rasos.

--update-shallow
Por padrão, ao buscar em um repositório superficial, o git fetch recusa os refs que
exigem atualização .git / shallow. Esta opção atualiza .git / shallow e aceita essas referências.

--dry-run
Mostre o que seria feito, sem fazer nenhuma alteração.

-k - Mantenha o pacote baixado.

--multiple
Permita que vários argumentos <repository> e <group> sejam especificados.




COMANDO DIFF

git-diff - Mostra mudanças entre confirmações, confirmação e árvore de trabalho, etc

OPÇÕES
-p
-U
--patch
Gere correção. Esse é o padrão.

-s
--no-patch
Suprimir saída diff. Útil para comandos como o git show que mostra
o patch por padrão ou para cancelar o efeito do --patch .

-U <n>
--unified= <n>
Gere diffs com <n> linhas de contexto em vez das três usuais. Implica --patch . Implica -p .

--output = <arquivo>
Saída para um arquivo específico em vez de stdout.

--raw
Gere o diff no formato bruto.

--patch-with-raw
Sinônimo para -p --raw .

--minimal
Gaste tempo extra para garantir que a menor diferença possível seja produzida.







4 - OPÇÕES
-t
Em vez do conteúdo, mostra o tipo de objeto identificado

-s
Em vez do conteúdo, mostra o tamanho do objeto identificado

-p
Imprime o conteúdo com base em seu tipo






COMANDO BUNDLE

git-bundle - Move objetos e referências por arquivo

OPÇÕES
create <arquivo>
Usado para criar um pacote nomeado arquivo. Isso requer os argumentos git-rev-list-args para definir o conteúdo do pacote.

verify <arquivo>
Usado para verificar se um arquivo de pacote configurável é válido e será aplicado de forma limpa ao repositório atual.

list-heads <file>
Lista as referências definidas no pacote configurável.

unbundle <arquivo>
Passa os objetos no pacote configurável para o git index-pack do armazenamento no repositório e depois imprime os nomes de todas as referências definidas.






COMANDO ARCHIVE

git-archive - Crie um archive de arquivos de uma árvore nomeada

OPÇÕES
--format = <fmt>
Formato do arquivo resultante: tar ou zip .

-i
--list
Mostrar todos os formatos disponíveis.

-v
--verbose
Relatar o progresso






