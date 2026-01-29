
### **LINUX.md**
```markdown
# Linux - Comandos Essenciais

## Sistema de Arquivos
```bash
# Navegação
pwd                     # Mostrar diretório atual
ls                      # Listar arquivos
ls -la                  # Listar detalhado
cd /caminho             # Mudar diretório
cd ~                    # Ir para home
cd -                    # Voltar ao anterior

# Manipulação
mkdir pasta             # Criar diretório
mkdir -p a/b/c          # Criar estrutura
rm arquivo              # Remover arquivo
rm -r pasta             # Remover recursivo
rm -rf pasta            # Forçar remoção
cp origem destino       # Copiar
cp -r origem destino    # Copiar recursivo
mv origem destino       # Mover/renomear
touch arquivo           # Criar arquivo vazio

# Permissões
chmod 755 arquivo       # Alterar permissões
chmod +x script.sh      # Tornar executável
chown user:group arquivo # Alterar dono
chown -R user:group pasta # Alterar recursivo

# Busca
find . -name "*.java"   # Buscar por nome
find . -type f          # Buscar arquivos
find . -mtime -7        # Modificados últimos 7 dias
find . -size +100M      # Maiores que 100MB
locate padrao           # Busca rápida (atualizar com updatedb)
grep "texto" arquivo    # Buscar texto
grep -r "texto" .       # Buscar recursivo


# Processos
ps aux                  # Listar todos processos
ps -ef | grep java      # Filtrar processos Java
top                     # Monitor em tempo real
htop                    # Top melhorado (instalar)
pkill processo          # Matar processo por nome
kill -9 PID             # Matar processo por PID
killall nome            # Matar todos com nome

# Sistema
uname -a                # Informações do sistema
df -h                   # Espaço em disco
du -sh pasta            # Tamanho de pasta
free -h                 # Memória livre
uptime                  # Tempo ligado e carga
lscpu                   # Informações da CPU
lsblk                   # Listar blocos/dispositivos

# Rede
ifconfig                # Configuração de rede (antigo)
ip addr show            # Configuração de rede (moderno)
ping google.com         # Testar conexão
netstat -tulpn          # Portas abertas
ss -tulpn               # Netstat moderno
curl url                # Fazer requisição HTTP
wget url                # Baixar arquivo
nslookup dominio        # Consulta DNS
dig dominio             # DNS mais detalhado

# Usuários
whoami                  # Usuário atual
who                     # Usuários logados
w                       # Usuários e processos
sudo comando            # Executar como root
su usuario              # Trocar usuário
passwd                  # Alterar senha
adduser usuario         # Adicionar usuário
deluser usuario         # Remover usuário
usermod -aG grupo usuario # Adicionar a grupo

# Grupos
groups usuario          # Grupos do usuário
addgroup grupo          # Criar grupo
delgroup grupo          # Remover grupo
getent group            # Listar todos grupos

# APT
sudo apt update         # Atualizar lista de pacotes
sudo apt upgrade        # Atualizar pacotes
sudo apt install pacote # Instalar pacote
sudo apt remove pacote  # Remover pacote
sudo apt purge pacote   # Remover com configurações
sudo apt autoremove     # Remover dependências não usadas
sudo apt search texto   # Buscar pacotes
apt list --installed    # Pacotes instalados
dpkg -L pacote          # Arquivos do pacote


# YUM/DNF
sudo yum update         # Atualizar pacotes
sudo yum install pacote # Instalar pacote
sudo yum remove pacote  # Remover pacote
sudo yum search texto   # Buscar pacotes
yum list installed      # Pacotes instalados

# DNF (Fedora)
sudo dnf install pacote
sudo dnf update


# Visualização
cat arquivo             # Mostrar conteúdo
less arquivo            # Visualizador paginado
tail arquivo            # Últimas linhas
tail -f arquivo         # Seguir atualizações
head arquivo            # Primeiras linhas
more arquivo            # Visualizar página a página

# Edição
nano arquivo            # Editor simples
vim arquivo             # Editor avançado
sed 's/old/new/g' arquivo # Substituir texto
awk '{print $1}' arquivo # Processar colunas

# Comparação
diff arquivo1 arquivo2  # Comparar arquivos
cmp arquivo1 arquivo2   # Comparar binários
comm arquivo1 arquivo2  # Comparar linhas comuns


# Tar
tar -czvf arquivo.tar.gz pasta/  # Compactar
tar -xzvf arquivo.tar.gz         # Extrair
tar -tzvf arquivo.tar.gz         # Listar conteúdo

# Zip
zip -r arquivo.zip pasta/        # Compactar
unzip arquivo.zip                # Extrair
unzip -l arquivo.zip             # Listar conteúdo

# Outros
gzip arquivo                     # Compactar
gunzip arquivo.gz                # Descompactar
bzip2 arquivo                    # Compactar com bzip2
bunzip2 arquivo.bz2              # Descompactar

# Firewall (UFW)
sudo ufw status                  # Status do firewall
sudo ufw allow 22/tcp            # Permitir porta
sudo ufw enable                  # Ativar firewall
sudo ufw disable                 # Desativar firewall

# SSH
ssh usuario@host                 # Conectar
ssh -p porta usuario@host        # Com porta específica
ssh-keygen                       # Gerar chaves
ssh-copy-id usuario@host         # Copiar chave

# Transferência
scp arquivo user@host:/caminho   # Copiar via SSH
rsync -avz origem destino        # Sincronizar


# Logs
journalctl -xe                    # Systemd logs
journalctl -f                    # Seguir logs
dmesg                            # Mensagens do kernel
tail -f /var/log/syslog          # Log do sistema
cat /var/log/auth.log            # Log de autenticação

# Desempenho
vmstat 1                         # Estatísticas do sistema
iostat 1                         # Estatísticas de I/O
mpstat 1                         # Estatísticas de CPU
sar                              # Coletor de estatísticas
iotop                            # I/O por processo
nethogs                          # Rede por processo





# Atalhos de terminal
Ctrl + A                       # Início da linha
Ctrl + E                       # Fim da linha
Ctrl + U                       # Limpar até início
Ctrl + K                       # Limpar até fim
Ctrl + R                       # Busca no histórico
Ctrl + L                       # Limpar tela
Ctrl + C                       # Cancelar
Ctrl + Z                       # Suspender
bg                             # Colocar em background
fg                             # Trazer para foreground

# Variáveis de ambiente
echo $PATH                     # PATH atual
export VAR=valor               # Definir variável
env                            # Todas variáveis

# Scripting avançado
set -e                         # Sair em caso de erro
set -x                         # Debug (mostrar comandos)
trap "comando" EXIT            # Executar ao sair



# Gerenciar containers
docker ps                       # Containers rodando
docker ps -a                    # Todos containers
docker images                   # Imagens locais

# Limpeza
docker system prune             # Limpar recursos não usados
docker volume prune             # Limpar volumes

# Logs
docker logs container           # Ver logs
docker logs -f container        # Seguir logs

# Permissões especiais
chattr +i arquivo               # Tornar imutável
lsattr arquivo                  # Listar atributos

# Sudo
sudo -l                        # Comandos permitidos
visudo                         # Editar sudoers

# Auditoria
last                           # Últimos logins
lastlog                        # Último login dos usuários
fail2ban-client status         # Status do fail2ban