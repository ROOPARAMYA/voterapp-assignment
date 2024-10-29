# edYoda_voterapp-assignmen
edYoda_assignment

2. Cloned voter app code from github by executing below command
   git clone https://github.com/ashishrpandey/example-voting-app

   - moved to example-voting-app
     
     cd  /root/example-voting-app/
     
   - listed files/ foleder present under example-voting-app  (CMD -> ls)
     
     LICENSE,  README.md,  docker-compose-javaworker.yml,  docker-compose.yml,  dockercloud.yml,    **result**,  **worker**
     MAINTAINERS, architecture.png, docker-compose-simple.yml, docker-stack.yml, k8s-specifications, **vote**
     
   - moved inside vote and analyzed docker config, app.py logic to get vote from user and communitcate same to redis, index.html code to render view of casting vote between         cats and Dogs.
     
   - moved inside worker directory and analized Dockerfile and program.cs file logic to establishing connection to redis and get voting data and establishing connection to        noSql DB and push data to DB.
     
   - moved inside result directory and analysized Dockerfile, server.js logic to establish connection with DB and get voting statistics and rendering the result using             index.html present under view folder and index.html logic.
  
3. cd k8s-specifications -> ls -> analized deployment and service yaml file content to create pods.
    db-deployment.yaml  redis-deployment.yaml  result-deployment.yaml  vote-deployment.yaml  worker-deployment.yaml
    db-service.yaml     redis-service.yaml     result-service.yaml     vote-service.yaml

    result and vote services exposing NodePort 31001 and 31000 respesticively for external access.
   
4. executed **kubectl apply -f .** command - it created all services and deploys
5. ![image](https://github.com/user-attachments/assets/d147924a-33c2-47a3-8e54-8126e9638ed1)

   
6. kubectl get all - gives all the Pods, SVC(service), Deploy and RS(resplica set) details.
    ![image](https://github.com/user-attachments/assets/cc4987b6-e55c-4266-a7f8-76ead9e408ba)

7. Able to access Vote and Result app from browser by accessing urls http://54.151.245.206:31000/ and http://54.151.245.206:31001/ respectively.
   
7. Able to cast vote and see updates in result app based on vote casted in voting app.
8. Deleted Vote Pod, worker pod and DB pod respectively using below command
   kubectl delete pod podName
   
9. Deleting vote pod, new the vote pod created. Applications(Vote and Result) are working fine able to cast vote and updated result is reflecting in result app.
   ![image](https://github.com/user-attachments/assets/8f3c446f-4649-49db-84c4-b6a73ecf83e8)
   ![image](https://github.com/user-attachments/assets/6dc4a9c1-0d74-43bf-9d69-60e313f08dcf)

   Deleting worker pod, new worker pod created.  Applications(Vote and Result) working fine able to cast vote and updated result is reflecting in result app.
   ![image](https://github.com/user-attachments/assets/bf785ccf-c18f-4ccf-ba2d-0083c834152c)
   ![image](https://github.com/user-attachments/assets/42730b67-b6ab-4548-8e4f-5e5f533f997a)

10. Deleting db pod, restarted DB container and result conatiner as well to establish connection with new DB container.   
   Applications(Vote and Result) working fine able to cast vote and updated result is reflecting in result app.
   ![image](https://github.com/user-attachments/assets/b0c4fbcd-2e6d-4af4-88bb-76c5b88cba6c)
11. 
