#Installer le toolbox de ceph
kubectl create -f toolbox.yaml
#Vérifier 
kubectl -n rook-ceph get pod -l "app=rook-ceph-tools"

#Utiliser
kubectl -n rook-ceph exec -it $(kubectl -n rook-ceph get pod -l "app=rook-ceph-tools" -o jsonpath='{.items[0].metadata.name}') bash

ceph status
ceph osd status
ceph df
rados df
When you are done with the toolbox, you can remove the deployment:

kubectl -n rook-ceph delete deployment rook-ceph-tools