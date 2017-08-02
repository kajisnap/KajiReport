## 리눅스 민트 설치 후 진행한 내용들 (20170801)

Linux Mint 18.1 Serena

- 다운로드 : http://linuxmint.com 


[[ 기본설치 후 한 일들 ]]

1. wifi 사용설정
  참고 : http://blog.naver.com/PostView.nhn?blogId=gracefulife&logNo=220733643163&parentCategoryNo=&categoryNo=19&viewDate=&isShowPopularPosts=false&from=postView

처음에 wifi 사용불가로 나옴
sudo lshw -C network (무선랜 장치 확인)
.. Qualcomm Atheros 6147 확인.. (이게 문제가 많댄다)

https://github.com/kvalo/ath10k-firmware/pull/3/files
에서 board-2.bin 선택

다운로드 폴더로 이동하여, 터미널을 키고  
sudo rmmod ath10k_pic 명령어를 날려준다. (모듈 삭제 명령어)

다음으로 sudo cp board-2.bin /lib/firmware/ath10k/QCA6174/hw3.0/board.bin
요래 쳐주면 원래있던 네트워크 드라이버 파일의 board.bin 파일을 덮어씌우게 된다.

그 후 재부팅을 하면된다.

[출처] 리눅스 민트 시나몬 무선 랜이 동작하지 않는 경우 - Qualcomm atheros (rev 32)|작성자 Gracefulife


2. 업데이트 관리자에서 각종 패키지 및 커널 업데이트

(유선랜으로 붙을 수 있었다면 커널 업데이트 부터 했을듯)
커널 업데이트 전에는 부팅이 10초 이상 걸렸으나, 
업데이트 후 재기동시 3초 이내 부팅 완료됨.
정확히 무엇 때문인지는 아직 모르겠음. 세세히 본게 아니라서..


3. 한영전환 설정

입력 - 한글 입력기 설치하고 재부팅 하면 Shift + Space 로 전환됨.
이전버전에서는 복잡하게 설정이 필요했던 것 같음.

현재 IBus 사용중이며, 
구글 크롬에서 전환이 잘 되지 않는 문제 발생.
대부분 다른 입력기로 갈아타라는 가이드가 많았음.

sudo apt-get install ibus-gtk ibus-gtk3
진행 후 해결됨.
(http://hellomo.co.kr/blog/?p=41)


4. 미디어 플레이어 설치

소프트웨어 관리자 - SMPlayer 설치로 간편하게 끝..
가끔 자막 인코딩이 맞지 않아 깨질때는
플레이어의 자막 인코딩 설정에서 적절히 바꿔준다.
VLC 플레이어 사용해도 되는데 일단 깔아봤다..




5. 시드마이어 문명5 리눅스 버전 설치
  잘된다. 영문판이지만.




6.  시트릭스 리시버 에러

     SSL Error 61: You have not chosen to trust thawte ssl ca 발생


https://discussions.citrix.com/topic/386275-you-have-not-chosen-to-trust-thawte-premium-server-ca-the-issuer-of-the-servers-security-certificate/

https://ubuntuforums.org/showthread.php?t=2221765



https://search.thawte.com/support/ssl-digital-certificates/index?page=content&id=AR1470

위 링크에서 [**Thawte Premium Server CA.pem**](https://symwisedownload.symantec.com/resources/sites/SYMWISE/content/live/GENERAL_INFORMATION/1000/INFO1470/en_US/Thawte%20Premium%20Server%20CA.pem?__gda__=1501822249_3475196dac1c0978665f58c67baf2caf) 파일 다운받은 후

/opt/Citrix/ICAClient/keystore/cacerts 이하에 넣어주면 됨.



이러고도 안뜰 때 Citrix 리시버 13.6 -> 13.4 재설치 후 정상동작 (데비안 계열 x86_64)



** 참고
리눅스를 설치한 후에 추가로 몇 개 프로그램을 더 설치해 줘야 한다. 
Adobe Flash Player, wine, winbind, Chrome,  PlayOnLinux 등이다. 
이것들을 다 설치하고 나면 카카오톡 PC버젼이나 MS Office 같은 자주 쓰는 윈도우용 프로그램을 설치하여 사용할 수 있다. 
이 설치 과정은 좀 까다롭기는 한데 민트 18.1 버젼에서는 안정화가 많이 되었는 지 별 무리 없이 설치가 되었다. 
윈도우용 프로그램을 설치하여 실행할 수 있도록 해 주는 프로그램이 PlayOnLinux와 wine 이라는 프로그램이다.

출처: http://pangate.com/932 [호주 멜번스토리]

