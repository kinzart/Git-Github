# git-github
Comandos e estrategias


          git --help



ajuda por html: (ex: comando "merge")
     
     
          git help merge



configurações:


         git config --global user.name "Seu nome e sobrenome"
         
         
         
         git config --global user.email "seuemail@email.com"
         
         
         
         git congig --global color.ui true




para vizualizar configurações: 


          git config --list
          
          
          git config user.name
          
          
          git config user.email




vizualizar mudanças por author:


         git log --author="nome"
         
         
vizualizar mudanças em uma linha por commit:


          git log --oneline


criar repositorio (uma pasta oculta git):


     git init
        

vizualizar mudanças e monitoramentos (o que esta dentro do git, estara em copias de segurança):


     git status


verificar o que foi codificado até o momento (vai mostrar os codigos que voce escreveu desde de o ultimo commit):


     git diff



verificar alterações apenas de um determinado arquivo:


     git diff arquivo.ex





criando branch, criando um clone para trabalhar fora da master:


     git checkout -b nome-do-branch
      

para listar os branches use o comando:


     git branch


para listar branches em repositorios remotos:


     git branch -a
     
     
     
para deletar uma branch:


     git branch -d nome-da-branch
     
     

depois de modificar um arquivo, podemos acessar as modificações com:


     git status

dessa forma:
 modified:   src/app/paginas/editar-pedido/editar-pedido.component.ts
 
 
 

adicionando as operações e as modificações:


     git add .
     


adicionando apenas determinada operação em um arquivo:


    git add nome-arquivo-modificado
    
    
    
    
concluindo as alterações (CHECKPOINT) aqui onde selecionamos uma descrição para o checkpoint:


    git commit -m "alteração 1"
    
    
    
subindo para o novo branch em seu repositorio github: 

    
    git push origin new-branch
  
  
  
 voltando para o branch master ou main:
  
  
    git checkout master
    
    git checkout main
  


mesclando os branch:


    git merge new-branch


adicionando os arquivos alterados no new-branch que agora esta mesclado com master ou main:


    git add .
    
    
concluindo alterações:


     git commit -m "concluindo a mesclagem com new-branch"
     

para alterar a mensagem do commit:


     git commit --amend
     
     
movendo arquivos para uma pasta:

         
     git mv arquivo.ex pasta-qual
     
movendo e renomeando:


    git mv arquivo.ex pasta-qual/arquivo-novo-nome
    


subindo o repositorio master para o github

     
     git push origin master
     
     git push origin main
    
    
vizualizar o historico:


     git log
     

vizualizar historico de um arquivo:


     git log -p nome-arquivo
     

historico de commits nas branchs:

     git log --all --decorate --oneline --graph
     
     
todos os commits

     git reflog
     
     
voltar para o commit (de marcação 1 por exemplo)

     git reset HEAD@{1}
     
     
se caso igual eu, voce ja deletou algo que queira restaurar de um commit, apos voltar ao commit:

          git status
          
restaurar um arquivo:
     
          git restore nome-arquivo
          
restaurar todos arquivos desse commit:

          git restore .



remover arquivo, remover do diretorio e depois remover do repositorio git:
          
          rm arquivo.ex
          
          git rm arquivo.ex




<h3>DESFAZENDO</h3>

restaurar ultimo commit do arquivo: ("--" branch atual)

          git checkout -- arquivo.ex
          

vizualizar restauração:

          
          cat arquivo.ex
          
          

refazer commit:


          git commit --amend -m "refazendo commit"
          
          
limpar pasta de arquivos nao adicionados na unstage area:

          git clean -n
          
          git clean -f


recuperando um estado especifico de um arquivo:
          
          git log


depois digite o codigo inicial da chave do commit
ex:

          git checkout 0b4df42 -- nome-arquivo.ext
          
          
          
          
<h3>RESET</h3>
atenção! reset muda seu ponteiro HEAD para um commit anterior

git log para listar


retrornar para commit especifico:


          git reset --soft 0a1b2c
          

retornar para commit especifico, sincronizando:

          
          git reset --mixed 0a1b2c
          
          
retornar para um commit especifico e apagar os que veio depois dele:

          git reset --hard 0a1b2c
          
 
 
 
 <h3>BRANCH</h3>
 
 
 Mostrar branchs
 
          git branch
          
          
 criar nova branch:
 
          git branch nova-branch
 
 
criar e migrar para uma nova branch:


          git checkout -b nova-branch
          
 

listar e confirmar:

          ls -la .git/refs/heads


vizualizar a HEAD

          cat .git/refs/heads/nova-branch
          
           cat .git/HEAD
           


vizualizar alterações entre branchs

          git show HEAD
          
          
          
vizualizar um grafico de ponteiros entre branch:


          git log --graph --oneline --decorate --all

          
comparando arquivos de duas branchs:


          git diff master..nova-branch
          
          
renomear uma branch:


          git branch --move nova-branch novo-nome
          
          
remover branch (só remove se estiver fora dela):


          git branch -d nome-branch
          

se caso esteja impedido de remover por alguma alteração sem commit:


          git branch -D nome-branch



<h3>MERGE</h3>



trazer alterações para mixar na master:


          git merge nova-branch


desfazer uma tentativa de merge:


          git merge --abort
          
          
 
 
 
<h3>GITHUB</h3>


listar o repositorio;


          git remote
          



adicionando um repositorio criado no github ao git (origin = pode ser qqr nome), (https:// = path que o seu repositorio apresenta): 


          git remote add origin https://github.com/kinzart/git-github.git
          
          
vizualizar repositorio remoto para push ou para download(fetch)


          git remote -v


          cat .git/config
          
          

deletar repositorio remoto:


          git remote rm origin
          


enviando arquivos para repositorio remoto, parametros(git push sincronismo nome-repo branch)


          git push -u origin master
          
          


