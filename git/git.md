
### **GIT.md**
```markdown
# Git - Comandos Essenciais

## Configuração Inicial
```bash
# Configurar usuário
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"

# Configurar editor padrão
git config --global core.editor "code --wait"

# Listar configurações
git config --list

# Configurar alias
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

# Configurar pull com rebase
git config --global pull.rebase true

# Habilitar coloração
git config --global color.ui auto


# Inicializar repositório
git init

# Clonar repositório
git clone https://github.com/usuario/repositorio.git
git clone https://github.com/usuario/repositorio.git meu-diretorio

# Clonar com submodules
git clone --recurse-submodules URL

# Verificar status
git status
git status -s            # Formato resumido

# Adicionar repositório remoto
git remote add origin URL
git remote -v            # Listar remotos
git remote rename origin novo-nome
git remote remove origin


# Adicionar arquivos
git add arquivo.txt
git add .               # Todos arquivos
git add *.java          # Padrão
git add -A              # Todos (incluindo removidos)
git add -p              # Adicionar por partes (patch)

# Commit
git commit -m "mensagem"
git commit -am "mensagem"  # Add + commit para arquivos rastreados

# Commit vazio (para triggers CI/CD)
git commit --allow-empty -m "Trigger build"

# Alterar último commit
git commit --amend
git commit --amend -m "Nova mensagem"
git commit --amend --no-edit  # Manter mensagem

# Commit assinado
git commit -S -m "mensagem"


# Ver histórico
git log
git log --oneline
git log --graph --oneline --all
git log -p arquivo.txt        # Com diferenças
git log --since="2024-01-01"
git log --author="nome"
git log --grep="palavra"
git log --stat                # Estatísticas
git log --pretty=format:"%h - %an, %ar : %s"

# Ver alterações específicas
git show commit-hash
git show HEAD                 # Último commit
git show HEAD:arquivo.txt     # Conteúdo em commit específico

# Buscar no histórico
git log -S "função"           # Buscar por string no código
git log -G "regex"            # Buscar por regex





# Listar branches
git branch
git branch -a                 # Todas (incluindo remotas)
git branch -r                 # Apenas remotas
git branch -v                 # Com último commit

# Criar branch
git branch nova-branch
git checkout -b nova-branch   # Criar e trocar

# Trocar branch
git checkout branch
git switch branch             # Nova forma (Git 2.23+)
git switch -c nova-branch     # Criar e trocar (nova forma)

# Renomear branch
git branch -m novo-nome
git branch -m antigo novo     # Renomear branch específica

# Deletar branch
git branch -d branch          # Deletar local
git branch -D branch          # Forçar deletar
git push origin --delete branch  # Deletar remota

# Acompanhar branch remota
git branch -u origin/branch
git branch --set-upstream-to=origin/branch


# Merge
git merge branch
git merge --no-ff branch      # Sem fast-forward
git merge --squash branch     # Unificar commits
git merge --abort             # Cancelar merge conflituoso

# Rebase
git rebase branch
git rebase -i HEAD~3          # Interativo (últimos 3 commits)
git rebase --continue         # Continuar após resolver conflitos
git rebase --abort            # Cancelar rebase
git rebase --skip             # Pular commit

# Rebase com autosquash
git rebase -i --autosquash

# Pull com rebase
git pull --rebase


# Salvar alterações temporárias
git stash
git stash save "mensagem"
git stash -u                  # Incluir arquivos não rastreados
git stash -a                  # Incluir todos arquivos

# Listar stashes
git stash list

# Aplicar stash
git stash apply               # Último stash
git stash apply stash@{2}     # Stash específico
git stash pop                 # Aplicar e remover

# Remover stash
git stash drop stash@{1}
git stash clear               # Remover todos

# Criar branch a partir do stash
git stash branch nova-branch stash@{1}


# Push
git push origin branch
git push -u origin branch     # Definir upstream
git push --all                # Todas branches
git push --tags               # Tags
git push --force              # Forçar (cuidado!)
git push --force-with-lease   # Forçar com segurança

# Pull
git pull origin branch
git pull --rebase origin branch

# Fetch
git fetch origin
git fetch --all
git fetch --prune             # Remover branches remotas excluídas

# Ver diferenças
git diff origin/branch..branch


# Criar tags
git tag v1.0.0
git tag -a v1.0.0 -m "Versão 1.0.0"
git tag -s v1.0.0 -m "Tag assinada"

# Listar tags
git tag
git tag -l "v1.*"            # Com padrão
git show v1.0.0              # Ver tag

# Push tags
git push origin v1.0.0
git push --tags

# Deletar tags
git tag -d v1.0.0
git push origin --delete v1.0.0

# Checkout tag
git checkout v1.0.0
git checkout -b branch v1.0.0  # Criar branch a partir da tag


# Reset
git reset HEAD~1             # Mover HEAD (mantém alterações)
git reset --soft HEAD~1      # Mantém alterações no staging
git reset --mixed HEAD~1     # Padrão (remove do staging)
git reset --hard HEAD~1      # Descarta tudo (cuidado!)

# Revert (cria novo commit desfazendo)
git revert HEAD
git revert commit-hash
git revert --no-commit HEAD~3..HEAD  # Vários commits sem commitar

# Limpar arquivos não rastreados
git clean -n                 # Simular (dry-run)
git clean -f                 # Remover arquivos
git clean -fd                # Remover arquivos e diretórios
git clean -x                 # Incluir arquivos ignorados