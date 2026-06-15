# memo.md


# host 의 8888 port 를 pod 의 80 port 로 연결해주는 NodePort 서비스 만들기
# 노출되는 node 의 port 는 30000 ~ 32767 사이에서 랜덤하게 배정이 된다.  
kubectl expose pod nginx-pod --type=NodePort --name=nginx-pod-svc --port=8888 --target-port=80 \
    --labels="color=blue"

# kubectl get svc 해서 배정된 port 번호를 확인한 다음 
kubectl get svc
NAME            TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes      ClusterIP   10.96.0.1      <none>        443/TCP          80m
nginx-pod-svc   NodePort    10.100.21.95   <none>        8888:30211/TCP   95s

# 모든 node 에 대해서 실행해 본다. 
http://172.16.8.10:30211
http://172.16.8.11:30211
http://172.16.8.12:30211


# 실습후에 vmware 를 끌때

master node 를 먼저 끄고 ->  node1, node2 를 끈다

# 다시 vmware 를 켤때

node1, node2 를 먼저 켜고 -> master node 를 킨다 
