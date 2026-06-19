
### Secret 사용하기

```bash

# 배포하고 
k apply -f .

# pod 안으로 들어가서 
k exec -it secret-test-deploy-5c7f6d956d-k26tx -- sh

# 환경변수값 확인하기 
echo $DB_PASSWORD

```

<img src="./assets/image01.png">
<img src="./assets/image02.png">