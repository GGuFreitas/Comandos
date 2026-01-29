
### **NPM.md**
```markdown
# NPM - Comandos Essenciais

## Gerenciamento de Projetos
```bash
# Inicializar novo projeto
npm init
npm init -y              # Pular perguntas

# Criar package.json com valores padrão
npm init --scope=@usuario

# Instalar pacote localmente
npm install pacote
npm i pacote             # Forma abreviada

# Instalar como dependência de desenvolvimento
npm install --save-dev pacote
npm i -D pacote

# Instalar globalmente
npm install -g pacote
npm i -g pacote

# Instalar versão específica
npm install pacote@1.2.3
npm install pacote@latest
npm install pacote@next   # Versão beta

# Instalar todas as dependências
npm install
npm ci                    # Instalação limpa (para CI/CD)


# Atualizar pacote
npm update pacote
npm update               # Todos os pacotes

# Remover pacote
npm uninstall pacote
npm rm pacote

# Remover globalmente
npm uninstall -g pacote


{
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js",
    "test": "jest",
    "build": "webpack --mode production",
    "lint": "eslint src/**/*.js"

}

# Executar scripts
npm start
npm run dev
npm run build
npm test
npm run lint

# Executar com parâmetros
npm run build -- --mode=development

# Verificar vulnerabilidades
npm audit
npm audit fix           # Corrigir automaticamente
npm audit fix --force   # Corrigir quebrando compatibilidade

# Gerar SBOM
npm sbom


# Login no npm registry
npm login

# Publicar pacote
npm publish

# Publicar com tag
npm publish --tag beta

# Cancelar publicação
npm unpublish pacote@version

# Deprecar versão
npm deprecate pacote@version "mensagem"

# Ver configurações
npm config list
npm config get registry

# Alterar registry
npm config set registry https://registry.npmjs.org/

# Configurar proxy
npm config set proxy http://proxy:8080
npm config set https-proxy http://proxy:8080

# Configurações úteis
npm config set save-exact true      # Salvar versões exatas
npm config set package-lock false   # Não gerar package-lock.json

# Limpar cache
npm cache clean --force

# Verificar cache
npm cache verify

# Definir cache personalizado
npm config set cache /caminho/para/cache

# Executar pacote sem instalação
npx create-react-app meu-app
npx eslint src/**/*.js

# Executar versão específica
npx pacote@version comando

# Executar pacote local
npx pacote-local

# Inicializar workspace
npm init -w packages/a

# Instalar em workspace específico
npm install pacote -w packages/a

# Executar script em todos workspaces
npm run build --workspaces

# Executar script em workspace específico
npm run test --workspace=packages/a


# Listar pacotes instalados
npm list
npm list --depth=0        # Apenas primeiro nível
npm list pacote          # Verificar versão específica

# Verificar por pacotes desatualizados
npm outdated

# Inicializar pacote privado
npm init --scope=@organizacao

# Pack - criar tarball
npm pack

# Link - desenvolvimento local
npm link                  # Criar link global
npm link ../meu-pacote    # Linkar pacote local
