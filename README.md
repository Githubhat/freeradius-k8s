<h2> freeradius-k8s</h1>
    <p>cd freeradius-k8s</p>
<h2>Create freeradius Pod using deployment file </h2>
    <p>kubectl create -f 01-deployment.yml</p>
<h2>Create freeradius Pod service using services file</h2>
    <p> kubectl create -f 02-services.yml</p>
<h2>Check Pod status</h2>
    <p>kubectl get pod -A</p>
<h2>Check service status</h2>
    <p>kubectl get svc</p>
<h2>Check service description details to get Internal and external NodePort information</h2>
    <p>kubectl describe svc lb-freeradius -n default</p>
<h2>Identify the worker node on which freeradius Pod is running using below command</h4>
    <p>kubectl get pods -o wide</p>
<h2>Testing freeradius authentication:</h3>
<p><b>Note:</b> The worker node IP on which POD is running need to be used for authentication testing </p>
<h2>Run the below command from all nodes: X denotes IP Address and Port </h4>
    <p>radtest testing password X.X.X.X:XXXX 0 SECRET</p>
