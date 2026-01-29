
## Extras Recomendados:

### **DOCKER.md** (opcional)
```markdown
# Docker - Comandos Essenciais

## Container
```bash
docker run imagem
docker run -d imagem          # Detached mode
docker run -p 8080:80 imagem  # Mapear portas
docker run -v /host:/container imagem  # Volumes
docker run --name meu-container imagem
docker run --rm imagem        # Remover após execução
docker run -e VAR=valor imagem # Variáveis de ambiente


docker ps
docker ps -a
docker stop container
docker start container
docker restart container
docker rm container
docker rm -f container        # Forçar remoção
docker logs container
docker logs -f container      # Seguir logs


docker build -t nome:tag .
docker images
docker rmi imagem
docker pull imagem
docker push imagem
docker save imagem > arquivo.tar
docker load < arquivo.tar


docker network ls
docker network create minha-rede
docker volume ls
docker volume create meu-volume
docker inspect container


docker-compose up
docker-compose up -d
docker-compose down
docker-compose logs
docker-compose build
docker-compose ps