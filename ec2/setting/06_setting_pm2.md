pm2는 Node.js의 프로세스 관리자이다. 총 2개의 nodejs 서비스(web app과 REST API)를 서버에서 운영할 예정인데 이를 모두 백그라운드로 돌려야한다. 
아니면 해당 서비스를 돌리면서 다른작업을 하기 힘들기 때문이다. 바로 전 글에서 mongodb를 백그라운드로 돌릴때 처럼 service나 systemctl 이용해서 프로세스를 관리하는것은 정말 어렵다. pm2에서 해준다는데 그냥 해주는거 받자.

자고 일어나서 할것: 기본적인 react-app, express-server 세팅 후 ecosystem.config.js 파일 작성하기.
이 후 스냅샷 찍어서 간직하기**


