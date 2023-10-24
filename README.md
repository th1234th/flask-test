# CI/CD With Jenkins, Python, Docker

- Project based Kumar
- update python requierement if need newest version
- if newest version like Flask, upgrade requierement to avoid dependences issues
    - itsdangerous
    - Jinja2
    - MarkupSafe
    - Werkzeug

To test the runnig app with kuberntes without using a Load balacer with minikube, use the following step:
    - Go to the kubeFiles directory
    - kubectl expose deployement app-deployment --type=NodePort --port=8080
    - minikube service app-deployment --url
    - ps -ef | grep docker@127.0.0.1 to review the tunnel port 
    - http://127.0.0.1:TUNNEL_PORT

Getting the NodePort using kubectl
    - kubectl get service app-deployment --output='jsonpath="{.spec.ports[0].nodePort}"'
