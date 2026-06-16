

```bash

k apply -f deploy.yaml
k apply -f service.yaml

```

### 외부 (window) 에서 webbrower 를 열어서  http://172.16.8.10:30001 로 요청해 보기
#### http://172.16.8.10:30001 , http://172.16.8.11:30001, http://172.16.8.12:30001 모두다 가능
<img src="./assets/image01.png">

```bash
# 실습후 마무리
k delete -f .
```