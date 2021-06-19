# argocd-demo


### Install Argo CD

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


### ArgoCD Kubernetes resource Output

pod/argocd-application-controller-0    
pod/argocd-dex-server-65f7d98b78-l8z92   
pod/argocd-redis-9567956cd-ndcc2         
pod/argocd-repo-server-d6ffd9d98-l48k5  
pod/argocd-server-5cbd9669f7-sgqcq       

                          
service/argocd-dex-server       
service/argocd-metrics          
service/argocd-redis            
service/argocd-repo-server      
service/argocd-server           
service/argocd-server-metrics   

                                 
deployment.apps/argocd-dex-server    
deployment.apps/argocd-redis         
deployment.apps/argocd-repo-server   
deployment.apps/argocd-server     

  
### Change 
service/argocd-server ==> Change from ClusterIP to NodePort


### Getting the login

Username: admin
Password: kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

#### Login

argocd login <argocd_server_IP:port> --username admin --password <output from above command>
  
#### Change credentials
  
argocd account update-password
  
  

  

