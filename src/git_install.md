# Ubuntu에서 git 설치 및 clone하기
1. sudo apt-get install git 명령어를 입력하여 패키지 리스트를 업데이트 합니다.   
2. sudo apt install git 명령어를 입력하여 깃을 설치합니다.   
3. git --version이라는 명령어를 입력하면 설치할 git의 버전을 알 수 있습니다.   
4. 아래 명령어를 입력하여 깃에 push했을 때 올라갈 내 정보를 입력해줍니다.   
```
git config --global user.name [이름]
git config --global user.email [메일 주소]
```
5. git clone [url 주소]를 입력하여 자신이 원하는 프로젝트를 깃으로부터 내려받습니다.
6. 홈에 가면 위와같이 내가 내려받았던 깃 프로젝트가 있는 폴더를 확인할 수 있습니다.

# Window에서 git 설치 및 clone하기
1. https://git-scm.com/downloads 링크되어 있는 페이지에 들어가서 자신의 OS에 맞는 Git 설치버전을 받는다.
2. 약관, 설치경로, Component 등을 읽으며 설정을하여 설치를 완료한다.
3. 깃을 처음 설치하면 Name과 Email이 Null로 되어있으므로 설치받은 GitBash를 열어서 아래의 명령어를 치고 설정을 해준다.
```
git config --global user.name [이름]
git config --global user.email [메일 주소]
```
4. 아래의 명령어를 입력하여 잘들어갔는지를 확인한다.
```
git config --list
```
5. clone할 디렉토리를 생성한 후 오른쪽 버튼을 클릭하여 'Git Bash Here'을 실행합니다.
6. git clone [url 주소]를 입력하여 자신이 원하는 프로젝트를 깃으로부터 내려받습니다.
7. 디렉토리에 들어가 내려받았던 깃 프로젝트가 있는지를 확인합니다.