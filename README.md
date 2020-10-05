# git-github
Comandos e estrategias


criar repositorio:

     git init
        

criando branch, trabalhando fora da master:

     git checkout -b nome-do-branch
      
      

depois de modificar um arquivo, podemos acessar as modificações com:

     git status
     
dessa forma:
 modified:   src/app/paginas/editar-pedido/editar-pedido.component.ts
 
 
 

adicionando as operações e as modificações:


     git add .
     


adicionando apenas determinada operação em um arquivo:

    git add nome-arquivo-modificado
    
    
    
    
concluindo as alterações (CHECKPOINT) aqui onde selecionamos um nome para o checkpoint:


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
     
     
subindo o repositorio master para o github

     
     git push origin master
     
     git push origin main
    
    
