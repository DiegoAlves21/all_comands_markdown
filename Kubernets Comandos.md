**kubectl api-resources** -> Listar todos os objetos que podem serem criados no kubernets

**kubectl api-resources | grep pod** -> Utilizando o grep para fazer filtro na lista

**kubectl apply 'AQUI ENTRA O POD.YAML'** -> 
Aplicando o arquivo de manifesto .yaml no kubernets

**kubectl get pods** -> Verificando todos os pods

**kubectl get all** -> Verificando tudo que tem rodando

**kubectl get po** -> Verificando todos os pods pelo short name 'po'

**kubectl get po -o wide** -> Verificando todos os pods com mais detalhes

**kubectl describe pod meupod** -> Verificando todos os detalhes de um pod específico

**kubectl port-forward pod/'MEUPOD' 8080:80** -> Redirecionando a porta do pod para porta da máquina

**kubectl delete pod 'MEUPOD'** -> Deleta o pod

**kubectl rollout history deployment 'MEUDEPLOY'** -> Lista a fila de deployments que foram criados

**kubectl rollout undo deployment 'MEUDEPLOY'** -> Faz o rollback para o deployment anterior ao que está em execução

**kubectl delete deploy <deployment name>** -> Deleta todos os deployments em execução

**k3d cluster create meucluster --servers 3 --agents 3 -p "30000:30000@loadbalancer"** -> Cria um cluster atribuindo a pota interna do container para a porta externa da máquina