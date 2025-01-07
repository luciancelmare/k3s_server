# k3s_server

# Server INIT

curl -sfL https://get.k3s.io | sh -s - server \
--token=GmeSWrngc3dPNgC \
--tls-san kube.lth.ro --tls-san 10.10.12.90 \
--cluster-init 


# Check for Ready node, takes ~30 seconds 
sudo k3s kubectl get node 



# SERVER 2,3,xxx - Join same cluster
curl -sfL https://get.k3s.io | sh -s - server \
--token=GmeSWrngc3dPNgC \
--tls-san kube.lth.ro --tls-san 10.10.12.90 \
--server https://10.10.12.81:6443
