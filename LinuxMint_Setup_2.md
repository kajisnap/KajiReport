## 리눅스 민트 설치 후 추가작업들 (20170802)



### 1. Ksnapshot 설치 

스크린샷용 - http://egloos.zum.com/zodiac12k/v/1273346



### 2. 깃 크라켄 설치 - https://www.gitkraken.com/download/linux-deb

http://eclipse4j.tistory.com/258 참고.
깃 크라켄이 민트 18.1에서 라이브러리 오류 있댄다.

hwi@hwi /usr/lib $ gitkraken
Node started time: 1501676450172
libcurl.so.4: cannot open shared object file: No such file or directory
Error: libcurl.so.4: cannot open shared object file: No such file or directory
    at Error (native)
    at process.module.(anonymous function) [as dlopen] (ELECTRON_ASAR.js:158:20)
    at Object.Module._extensions..node (module.js:568:18)
    at Object.module.(anonymous function) [as .node] (ELECTRON_ASAR.js:169:18)
    at Module.load (module.js:456:32)
    at tryModuleLoad (module.js:415:12)
    at Function.Module._load (module.js:407:3)
    at Module.require (module.js:466:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/usr/share/gitkraken/resources/app.asar/node_modules/nodegit/dist/nodegit.js:11:12)
    at Module._compile (module.js:541:32)
    at Object.Module._extensions..js (module.js:550:10)
    at Module.load (module.js:456:32)
    at tryModuleLoad (module.js:415:12)
    at Function.Module._load (module.js:407:3)
    at Module.require (module.js:466:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/usr/share/gitkraken/resources/app.asar/src/appBootstrap/upgradeScripts/versionScripts/v1_5_0.js:7:17)
    at Module._compile (module.js:541:32)
    at Object.Module._extensions..js (module.js:550:10)
    at Module.load (module.js:456:32)
    at tryModuleLoad (module.js:415:12)
    at Function.Module._load (module.js:407:3)
    at Module.require (module.js:466:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/usr/share/gitkraken/resources/app.asar/src/appBootstrap/upgradeScripts/versionScripts/index.js:5:28)
    at Module._compile (module.js:541:32)
    at Object.Module._extensions..js (module.js:550:10)
    at Module.load (module.js:456:32)
    at tryModuleLoad (module.js:415:12)
    at Function.Module._load (module.js:407:3)
    at Module.require (module.js:466:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/usr/share/gitkraken/resources/app.asar/src/appBootstrap/upgradeScripts/index.js:7:24)
    at Module._compile (module.js:541:32)
    at Object.Module._extensions..js (module.js:550:10)
    at Module.load (module.js:456:32)
    at tryModuleLoad (module.js:415:12)
    at Function.Module._load (module.js:407:3)
    at Module.require (module.js:466:17)
    at require (internal/module.js:20:19)
    at EventEmitter.module.exports.app.on (/usr/share/gitkraken/resources/app.asar/src/appBootstrap/main.js:174:5)
    at emitOne (events.js:101:20)
    at EventEmitter.emit (events.js:188:7)


sudo ln -sf /usr/lib/x86_64-linux-gnu/libcurl-gnutls.so.4.4.0 libcurl.so.4
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get install libstdc++-4.9-dev

이까지 하고도 안될 경우 하나 더..

sudo apt-get install curl libcurl3



### 3. Typora 설치

http://macnews.tistory.com/4799

https://www.typora.io/#linux
- optional, but recommended

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
- add Typora's repository

sudo add-apt-repository 'deb https://typora.io ./linux/'
sudo apt-get update
- install typora

sudo apt-get install typora





### 4. 파이썬 설치

이미 설치되어 있음.

없을 경우 - hwi@hwi /usr/bin $ sudo apt-get install python3.5


버전확인

hwi@hwi /usr/bin $ python3 --version
Python 3.5.2
hwi@hwi /usr/bin $ python2 --version
Python 2.7.12



참고 : https://tutorial.djangogirls.org/ko/python_installation/#debian--ubuntu



### 5. Anaconda 설치

http://blog.naver.com/PostView.nhn?blogId=radii26omg&logNo=220752257115&parentCategoryNo=&categoryNo=7&viewDate=&isShowPopularPosts=true&from=search

경로는 자신의 경로에 맞게 잘 쓰자.

http://egloos.zum.com/mataeoh/v/7052271



http://goodtogreate.tistory.com/entry/IPython-Notebook-%EC%84%A4%EC%B9%98%EB%B0%A9%EB%B2%95 이건 나중에 볼 예정.

http://bryan7.tistory.com/720