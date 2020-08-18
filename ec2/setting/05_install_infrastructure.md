[Ubuntu에 Node.js 설치하기](https://github.com/nodesource/distributions/blob/master/README.md#debinstall)
<br />
<br />
[Ubuntu에 mongodb 설치하기](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
<br />
주의할 점으로는 ubuntu 20.04 버전이 아닌 18.04 버전을 설치해야된다. 무심결에 넘어갔다가는 상위버전의 source list를 받아서 제대로 설치를 못하게 되는 경우가 발생한다. 그리고 Access deny도 당하며, system daemon도 제대로 동작하지 않게된다. 경험담이다..  
<br />
<br />
가끔 sudo 커맨드들이 섞여서 나온다. 특히 Node.js와 mongodb의 설치 과정은 root 계정으로 진행하는것이 좋다.  
<br />
<br />

그다음 woo 계정으로 사용자 전환을 해준 다음 express, react, react-router-dom... 등등의 모듈들을 설치해준다.
