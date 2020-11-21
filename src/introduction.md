# 들어가기에 앞서

여러분들이 unibook을 사용하기에 앞서 필요한 준비물이 있습니다. 지금부터  
__Visual Studio Code(VScode)__  
__bash__  
__gcc__  
__macOS/Window/Linux__  
__GitHub__  
__StackOverflow__  
에 대한 간단한 설명과 실행/사용법을 순서대로 알려드리겠습니다.

## Visual Studio Code(VScode)
: 마이크로소프트에서 개발한 **문서 편집기**로, txt, C, C++등 다양한 확장자의 문서를 편집할 수 있습니다. macOS, Window, Linux의 모든 운영체제 지원합니다.

### 설치(macOS, Window, Linux)

### 1 macOS
    준비중
    
### 2 Windows
  https://code.visualstudio.com/ 로 이동하여 vscode를 다운받습니다.  
  ![vscodeDownload_window](./img/vscodeDownload_window.png)

  다운 완료 후 첫 실행화면입니다.  
  ![vscodeDowload_window_1](./img/vscodeDownload_window_1.png)

  다음의 아이콘을 선택하면 필요한 extension(확장프로그램)을 설치할 수 있습니다.(Ctrl+Shift+x)  
  ![vscodeDownload_window_2](./img/vscodeDownload_window_2.png)
    

### 3 Linux
  Linux에서는 macOS나 Windows와 다르게 터미널 창에서 VScode를 설치할 수 있습니다.(터미널은 Ctrl+Alt+T 단축키로 열 수 있습니다.)

  명령어 입력으로 우선 컴파일러부터 설치해줍니다.  
  __sudo apt-get install build-essential__

  설치가 완료되면 아래의 명령어를 입력하여 정상설치 되었는지 확인합니다.  
  __gcc --help__


  이어서 VScode를 설치해보겠습니다.

1 MS의 GPG를 다운받기 위한 curl 패키지를 설치합니다.  
__sudo apt-get install curl__

2 GPG를 다운받아서 /etc/apt/trusted.gpg.d/ 경로에 복사합니다.  
__sudo sh -c ' curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > /etc/apt/trusted.gpg.d/microsoft.gpg'__

3 VScode를 다운받기 위한 저장소를 /etc/apt/sources.list.d/ 경로에 추가해주겠습니다.  
__sudo sh -c ' echo " deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main " > /etc/apt/sources.list.d/vscode.list '__

4 패키지를 다운받았으므로 업데이트를 해줍니다.  
__sudo apt-get update__

5 VScode를 설치합니다.  
__sudo apt-get install code__

6 3에서 추가했던 저장소를 삭제합니다.  
__sudo rm /etc/apt/sources.list.d/vscode.list__

VScode의 설치가 완료된 후, 터미널 창에 code라고 입력하여 VScode를 실행시킬 수 있습니다.  
![vscodeDownload_linux](./img/vscodeDownload_linux.png)

VScode를 실행시킨 후, Extentions(Ctrl+Shift+X)창을 열어서 원하는 확장 프로그램을 설치해줍니다.  
우선 C/C++을 설치해보겠습니다.  
![vscodeDownload_linux_1](./img/vscodeDownload_linux_1.png)

Open Folder(Ctrl+Shift+E)에서 작업할 폴더를 선택할 수 있습니다.  
![vscodeDownload_linux_1](./img/vscodeDownload_linux_1.png)

다음으로 Terminal -> Configure Default Build Task... -> Create tasks.json file from template -> MSBuild  
순으로 선택하여 tasks.json 파일을 아래와 같이 수정합니다.  
     {
     
      "version": "2.0.0",
      "runner": "terminal",
      "type": "shell",
      "echoCommand": true,
      "presentation": {"reveal": "always"},
      "tasks": [
          //C++
          {
              "label":"save and compile C++",
              "command":"g++",
              "args":[
                  "-g3"
                  "${file}",
                  "-o",
                  "${fileDirname}/${fileBasenameNoExtension}"
              ],
              "group": "build",

              "problemMatcher":{
                  "fileLocation":[
                      "relative",
                      "${workspaceRoot"
                  ],
                  "pattern": {
                      "regexp":"^(.*):(\\d+):(\\d+):\\s+(warning error):\\s+(.*)$",
                      "file":1,
                      "line":2,
                      "column": 3,
                      "severity": 4,
                      "message": 5
                  }
              }
          },
    //C

          {
              "label":"save and compile C",
              "command":"gcc",
              "args":[
                  "-g3"
                  "${file}",
                  "-o",
                  "${fileDirname}/${fileBasenameNoExtension}"
              ],
              "group": "build",

              "problemMatcher":{
                  "fileLocation":[
                      "relative",
                      "${workspaceRoot"
                  ],
                  "pattern": {
                      "regexp":"^(.*):(\\d+):(\\d+):\\s+(warning error):\\s+(.*)$",
                      "file":1,
                      "line":2,
                      "column": 3,
                      "severity": 4,
                      "message": 5
                  }
              }
          },

          {
              "label": "execute",
              "command":"cd ${fileDirname} && ./${fileBasenameNoExtension}",
              "group": "test"
          }
      ]
    }


이제 마지막입니다. File -> Preference -> Keyboard Shortcuts(Ctrl+K Ctrl + S)  
로 이동하여 keybindings.json 파일을 아래와 같이 수정합니다.(컴파일/실행 단축키를 설정하는 것입니다.)  

// Place your key bindings in this file to override the defaults
[
    //compile
    { "key": "ctrl+shift+1", "command":"workbench.action.tasks.build"},
    //execution
    { "key": "ctrl+shift+2", "command":"workbench.action.tasks.test"}
]

## bash

## gcc

## macOS/Window/Linux

## GitHub

## StackOverflow
