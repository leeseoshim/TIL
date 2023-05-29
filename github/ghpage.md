# github page 배포

    npm i gh-pages

결과물을 github pages에 업로드 할 수 있게 해준다.

github pages는 github에서 제공하는 무료 서비스이고, 결과물을 웹사이트로 만들어서 전세계에 무료로 배포해준다.

<br/>

## 배포 방법

1.  package.json의 마지막줄에 콤마찍고 추가하거나 첫번째 줄에 아래 코드를 적어서 url를 지정한다.

        "homepage": "https://깃헙유저이름.github.io/깃헙리파지토리 이름"

\*git remote -v를 쳐보면 리파지토리이름 확인 가능

2.  package.json의 script 안에
    "deploy":"gh-pages -d build" 추가

설치한 gh-pages를 실행시키고, build 디렉토리를 가져간다.

3.  build하고 나서 deploy를 또 해야하는게 귀찮기때문에 deploy아래에 predeploy를 추가해서 npm run deploy만 해도 build까지 되게끔 만든다.

        "predeploy":"npm run build"

npm run build를 실행하면 production ready code를 생성하게 된다.
production ready란 코드가 압축되고 모든게 최적화 된다는 의미이다.

build가 끝나면 build폴더가 생성된다.

<br/>

# 실행 흐름

npm run deploy를 실행시키면 자동으로 predeploy가 실행되면서 npm run build가 실행되고, npm run build가 react-scripts build를 실행이 되서 빌드파일을 만들어준다.

마지막으로 gh-pages -d build가 실행돼서 gh-pages가 build폴더를 homepage에 적어놓은 url로 배포해준다.

## npm run build

코드를 압축하고 최적화시켜서 build폴더에 만들어줌

## deploy

gh pages가 build폴더를 적어둔 웹사이트에 업로드해준다.
