이전과 같이
```
pm2 ecosystem
```
커맨드로 이번에는 /home/woo/express-server/ecosystem.config.js 파일을 만든다.
그리고 ecosystem.config.js를 다음과 같이 작성해준다.

```
module.exports = {
  apps: [{
  name: 'api-server',
  script: 'index.js',
  watch: true,
  ignore_watch: ['node_modules'],
  wait_ready: true,
  listen_timeout: 5000,
  kill_timeout: 4000
  }]
}
```

이제 위의 script에 들어간 index.js 파일을 작성해보자. pm2와 신호를 처리하는 부분을 작성해보겠다. 

```
// express-server/index.js

const http = require('http');
const express = require('express');

const app = express();
const port = 7777;
const server = http.createServer(app);

// server에 'SIGINT'가 오는 경우, close한다. 
process.on('SIGINT', () => {
  console.log('close server');
  server.close(() => {
    console.log('Server gracefully closed')
  })
)


// server가 포트에 연결되면 pm2로 'ready' 신호를 보내게 한다.
server.listen(port, () => {
  process.send('ready')
  console.log(`Server is ready on tcp:${port} ports`)
  }
)
```

주석 이외에 설명할점은, server.close()의 경우 서버 프로세스의 삭제를 의미하지 않는다. 더 이상 새로운 connection을 하지 않고, 현재의 connection만을 유지하겠다는 의미이다. kill_timeout이 4초이니, 'SIGINT'를 받아들이고 여태까지 connection된 request들만 처리해주는데 4초를 준다. 4초 이후에는 pm2에서 서버 프로세스로 'SIGKILL'을 보내게 되어 4초동안 해결되지 않은 request들은 응답을 받을 수 없게된다.
