# docker-vscode_server
docker-compose of VScode server(code-server)

## repository 제작 배경
* vscode를 아이패드같이 브라우저 환경에서 쓰고 싶었음. 서버에 직접 설치하여 웹브라우저로 접속하기 위함.
* vscode server(=code-sever)설치 방법이 여러가지 있으며 script 버전 설치시 서비스를 올리고 내리는데 다른 사용자와 관리자와의 의사소통이 불편하여 docker로 설치하려 함.

## run
1. git clone
2. 호스트서버(내가 작업하는 서버)의 dir변경
```bash
  vi docker-compose.yaml 
  
  volumes:
  - "(YOURDIR):/home/coder/project"
  # ex) - "/:/home/coder/project"
```
3. user와 port번호 변경
```bash
  vi run_vscode.sh
  
  MYPORT=(YOURPORT) USER=(YOURSERVER_ID) MYUID=$(id -u) MYGID=$(id -g) PASSWORD=ducke docker-compose up -d
  # ex) MYPORT=9090 USER=kehyeong MYUID=$(id -u) MYGID=$(id -g) PASSWORD=ducke docker-compose up -d
```
4. 실행
```bash
sh run_vscode.sh
```

5. 브라우저 접속
![image](https://user-images.githubusercontent.com/54048026/146728583-5b79c2cd-84bc-46c9-aaa0-e56f6e0be77e.png)

## reference
1. https://bundw.tistory.com/entry/VSCode-%EB%8F%84%EC%BB%A4Docker%EB%A1%9C-docker-compose-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%9B%B9IDE-%EA%B5%AC%EC%B6%95-code-server
2. https://hub.docker.com/r/codercom/code-server
