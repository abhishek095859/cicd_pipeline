# kubernetes day3
# Web application on kubernets
In this application we have mongodb , mongo-express , secrets , services , configmaps
firstly we need to start the minikube 
# minikube start

then create secure credentials
# kubectl apply -f mongo-secret.yaml
to check the credentials
# kubectl get secrets
![Screenshot 2025-06-21 104502](https://github.com/user-attachments/assets/164d2cf3-991a-4060-a7fb-7a46b223f75a)



then deploy the mongo-db backend by 
# kubectl apply -f mongo-deployment.yaml
to view all the resources 
# kubectl get all
![Screenshot 2025-06-21 104549](https://github.com/user-attachments/assets/25607bc1-7ed2-4f1c-8676-0cd743efb6a9)


then create the configmap for the non senstivite data
# kubectl apply -f mongo-configmap.yaml
to view the configmaps 
# kubectl get configmaps
![Screenshot 2025-06-21 104617](https://github.com/user-attachments/assets/d8a378ba-0106-47d7-b0d5-3f108df6cd88)


then create the mongo-express for the frontend admin interface
# kubectl apply -f mongo-express.yaml
![Screenshot 2025-06-21 104659](https://github.com/user-attachments/assets/fc477f99-3c52-47e7-b89e-8466743e0004)

to get the service URL and open in browers
# minikube service mongo-express-service
![Screenshot 2025-06-21 144206](https://github.com/user-attachments/assets/436f184e-7626-4e8b-9d6b-3836cd1f80e2)

then brower will display the logging option to access the mongodb 
then enter the user name as my-admin-user
and password as my-super-password 
![Screenshot 2025-06-21 144145](https://github.com/user-attachments/assets/3f788623-a035-4e96-821b-cfc202bb767e)

then we can access the mongodb interface and we can create a database and also we can delete 
![Screenshot 2025-06-21 143944](https://github.com/user-attachments/assets/e3ff53db-0d00-48d3-b449-7862efcf3a81)


to clean up all the resources 
kubectl delete -f mongo-express.yaml
kubectl delete -f mongo-deployment.yaml
kubectl delete -f mongo-configmap.yaml
kubectl delete -f mongo-secret.yaml

