# 1. o histórico completo, com a topologia
*   0a33d82 (HEAD -> main, origin/main) Merge branch 'feature/guia-de-estilo'
|\  
| *   2104df4 Merge branch 'feature/tipografia' into feature/guia-de-estilo
| |\  
| | * 41ac951 adicionar novo guia de estilo
| | * 2bc3133 adicionar guia de estilo
| * | b571a2e adicionar agenda ao readme
| * | 4212d2a novo guia de estilo
| |/  
| * 4065324 guia de estilo
* |   3d6545f Merge branch 'chore/limpeza'
|\ \  
| * | 04e3705 apagar arquivo rodapé
| |/  
* |   66b34cc Merge branch 'feature/abertura'
|\ \  
| * \   e72d844 Merge branch 'main' into feature/abertura

# 2. devem existir 21 commits alcançáveis pela main, sendo 6 de merge
git rev-list --count HEAD
22
git rev-list --merges --count HEAD
6

# 3. só pode restar a main, local e remota
git branch -a
* main
  remotes/origin/main

# 4. nenhum marcador de conflito pode ter sobrado em arquivo nenhum
PS C:\Users\fhscheid\Documents\gerencia-config-ex1> Get-ChildItem -Recurse -File -Exclude .git | Select-String '<<<<<<<'
PS C:\Users\fhscheid\Documents\gerencia-config-ex1> 

# 5. todo link relativo do manual precisa apontar para um arquivo que existe;
#    liste os links e confira um por um
PS C:\Users\fhscheid\Documents\gerencia-config-ex1> Get-ChildItem -Recurse -File | Where-Object { $_.FullName -notmatch '\\.git\\' } | Select-String '\]\(docs/'

README.md:5:- [Sobre a mostra](docs/sobre.md)
README.md:6:- [Agenda](docs/agenda.md)