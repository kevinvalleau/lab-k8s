# lab-k8s
Dépôt de fichiers laboratoires pour kubernetes


# Déploiement sur un playground docker (PWD ou Katacoda)

Télécharger et installer kind : 

curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.8.1/kind-$(uname)-amd64
chmod +x ./kind
mv ./kind /usr/local/bin/kind

Télécharger et installer kubectl : 
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kind
mv ./kubectl /usr/local/bin/kubectl

utiliser un dépôt github avec curl pour récupérer les fichiers yaml en local et les exécuter
par exemple :
curl https://raw.githubusercontent.com/kevinvalleau/lab-k8s/master/workload-stateful-mysql/mysql-statefulset.yaml > mysql-statefulset.yaml
Cela va créer le fichier en local et ensuite on peut lancer : 
kubectl apply -f mysql-statefulset.yaml