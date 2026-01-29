# Shebang para scripts
#!/bin/bash
#!/usr/bin/env python3

# Variáveis
VAR="valor"
echo $VAR

# Condicionais
if [ condição ]; then
  comando
fi

# Loops
for i in {1..10}; do
  echo $i
done

while [ condição ]; do
  comando
done

# Funções
minha_funcao() {
  echo "Função executada"
}

# Execução
./script.sh                     # Executar script
bash script.sh                  # Executar com bash
sh script.sh                    # Executar com sh
source script.sh                # Executar no shell atual


date                            # Data e hora atual
date "+%Y-%m-%d %H:%M:%S"       # Formato específico
cal                             # Calendário
cal 2024                        # Calendário do ano
timedatectl                     # Configuração de data/hora
timedatectl set-timezone America/Sao_Paulo


# Terminal
clear                           # Limpar terminal
history                         # Histórico de comandos
!!                              # Último comando
!comando                        # Último comando começando com...
alias ll='ls -la'               # Criar alias
which comando                   # Localizar executável
whereis comando                 # Localizar binário, fonte e man

# Informação
man comando                     # Manual
info comando                    # Info pages
whatis comando                  # Breve descrição
apropos palavra                 # Buscar por descrição

# Particionamento
fdisk -l                        # Listar partições
lsblk                           # Listar blocos
blkid                           # Identificar partições

# Montagem
mount /dev/sda1 /mnt            # Montar partição
umount /mnt                     # Desmontar
df -h                           # Espaço usado

# Formatação
mkfs.ext4 /dev/sda1             # Formatar como ext4
fsck /dev/sda1                  # Verificar sistema de arquivos