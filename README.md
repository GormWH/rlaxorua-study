# rlaxorua-study

김태겸 공부 시키기

## 목적

웹 개발자가 되는 것에 관심은 있는데 뭐가 뭔지 모르는 사람을 위해 찍먹 코스를 만들어 봤다.

## 과제

어디까지나 찍먹이기 때문에 프로그래밍 하는 기분을 낼 수 있는 정도의 간단한 웹사이트 만드는 것을 최종 목표로 설정했다.

- [ ] 1. 컴퓨터 세팅
- [ ] 2. HTML, CSS, JavaScript 기초 공부
- [ ] 3. 간단한 웹사이트 만들기

## 1. 컴퓨터 세팅

Nomad Coders의 '개발자를 위한 윈도우 셋업'을 직접 들으면서 중요한 내용만 간략히 정리해 보았다.  
무료 강의이기 때문에 직접 들으면서 따라해
강의URL : <https://nomadcoders.co/windows-setup-for-developers/lobby>

> 예상 소요 시간

5시간 정도. 순수 강의 시간은 2시간 ~ 2시간 반 정도인것 같지만 실제로 따라하려면 두배 정도 시간은 걸릴 것 같다.

> 이 과정에 대한 작성자의 생각

강의에 소요되는 시간의 절반 정도가 Terminal과 VSC를 더 예쁘게 꾸미는(?) 데에 사용된다.  
불필요한 작업 같아 보이지만 오랜 시간 Terminal과 코드를 쳐다봐야 하는 것을 고려하면 시각적인 요소를 개선하는 것이 생산성에 좋은 영향을 미칠 것 같다.  
처음에 설정해두면 좋은 것 같다.

윈도우 셋업에 관한 강의지만 vsc, zsh 설정이나 nvm을 이용한 node 버전 관리 등은 맥에서도 충분히 활용 가능한 내용들이다.

### 1-1. Chrome, Git, VSC 설치

크롬 브라우저와 Git, Visual Studio Code를 검색해 설치한다.  
**VSC설치시 설치 옵션을 선택하는 부분이 있는데 전부 다 체크해서 설치하는 것이 좋다.**  
VSC는 코딩을 편리하게 해줄 각종 extension도 설치한다.

> 설치할 VSC Extension 목록

- Python
- Material Theme
- Material Icon Theme
- ESLint
- Prettier - Code formatter

### 1-2. Windows Terminal 설치

microsoft store에서 Windows Terminal을 설치한다.  
설치 링크 : <https://www.microsoft.com/store/productId/9N0DX20HK701>

### 1-3. WSL 설치(+ Ubuntu설치)

MS공식 문서(<https://docs.microsoft.com/ko-kr/windows/wsl/install>)에 따르면 아래 코드 한줄로 WSL 설치가 끝난다.

```
wsl --install
```

> '관리자 권한으로 실행'한 power shell 혹은 windows terminal에서 수행해야한다.

꼭 관리자 권한으로 실행한 터미널에서 위 코드를 작성해야 설치가 진행된다.  
강의에선 훨씬 복잡하게 진행되는데 최근 윈도우 업데이트 이후론 코드 한줄로 WSL2 및 Ubuntu 설치까지 자동으로 진행되는 모양이다.

### 1-4. Terminal 커스텀

예쁘게 꾸미는 시간이다.  
자잘한게 너무 많이 강의를 자세히 보는걸 추천한다.

> VSC에서 Remote - WSL라는 extension도 추가해준다.

> 터미널 설정

terminal > 설정 > json파일열기  
를 통해 설정과 관련된 json파일을 볼 수 있다.  
잘 모른다면 'json파일열기' 말고 다른 버튼은 안 건드리는 것을 추천한다.  
강의에선 shell목록 변경 및 default shell 설정을 한다.

> zsh 설치

zsh설치 공식 문서(<https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH>)  
위 문서 Ubuntu에서의 설치 방법을 따라

```
sudo apt install zsh
```

라고 입력하면 된다.
여기서 'sudo'는 관리자(admin)가 아닌 사용자가 관리가 권한으로 명령을 실행할때 필요한 단어다.

> oh my zsh 설치

oh my zsh 공식 문서(<https://github.com/ohmyzsh/ohmyzsh>)
위 문서의 내용에 따라

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

위 코드를 입력하면 설치가 진행된다.

> powerlevel10k 설치

powerlevel10k 공식 문서(<https://github.com/romkatv/powerlevel10k>)
위 문서 내용에 따라 아래 코드를 입력한다.

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

```
code ~/.zshrc
```

라고 입력해 zsh설정 파일을 열어

```
ZSH_THEME="~~~~"
```

라고 써있는 부분을

```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

이렇게 고쳐준다.  
아래 네개의 링크에서 폰트를 다운 받고 다운 받은 파일을 열어 전부 다 설치해 준다.  
<https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf>  
<https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf>  
<https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf>  
<https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf>  
VSC 그리고 Windows Terminal에서 폰트를 위에서 다운 받은 MesloLGS NF로 변경한다.  
강의에 자세히 설명되어 있지만, 공식 문서에서 필요한 부분을 복사해 왔다.

- Visual Studio Code: Open File → Preferences → Settings (PC) or Code → Preferences → Settings (Mac), enter terminal.integrated.fontFamily in the search box at the top of Settings tab and set the value below to MesloLGS NF.
- Windows Terminal by Microsoft (the new thing): Open settings.json (Ctrl+Shift+,), search for fontFace and set the value to MesloLGS NF for every profile. If you don't find fontFace, add it under profiles → defaults.

여기까지 완료 후 터미널에 들어가보면 powerlevel10k 설정 화면이 뜨는데 원하는 대로 설정하면 된다.

### 1-5. 리눅스 튜토리얼

리눅스 내부(`/home/`)에 작업 파일들을 두면 WSL환경에 문제가 생겼을 때 파일들이 날라갈 수 있기 떄문에 윈도우(`/mnt/c/`)에 작업 파일을 둘 것을 권장하고 있다.

> 리눅스에서 많이 사용하는 명령어들

- ls
- cd
- mv
- touch
- mkdir
- rm

> `ls`(list)

현재 디렉토리 내에 있는 파일, 폴더를 터미널에 출력한다.  
`.`으로 시작하는 파일들은 숨겨져 있어서 `ls` 만으론 볼 수 없는 경우가 있는데 `ls -a` 라고 입력하면 숨겨진 파일들도 표시할 수 있다.

> `cd`(change directory)

`cd` 뒤에 이동하고자 하는 디렉토리를 입력하면 그 디렉토리로 이동한다.

> `mv`(move)

`mv <현재 파일위치/파일명> <이동 후 파일위치/파일명>`  
위와 같이 입력해 파일을 이동시키거나, 이름을 변경할 수 있다.

> touch

`touch <파일명>`으로 파일을 생성할 수 있다.

> mkdir

`mkdir <폴더명>`으로 폴더를 생성할 수 있다.

> rm

`rm <파일명>` 혹은 `rm -rf <폴더명>`으로 파일 혹은 폴더를 삭제할 수 있다.

### 1-6. deadsnakes를 이용한 Python 설치(Ubuntu에서만 가능)

deadsnakes(<https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa>)  
deadsnakes팀의 ppa를 이용해 다양한 버전의 파이썬을 설치 그리고 필요에 따라 변경해서 사용할 수 있다.

```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
```

공식 문서 내용에 따라 위 코드를 입력하면 deadsnakes팀에서 만든 설치 리스트를 Ubuntu에서 인식할 수 있게 된다.

이제 Python을 어디에서 다운 받아야할지 Ubuntu에서 알기 때문에  
`sudo apt-get install python3.8`  
라고 입력해 Python3.8을 다운 받는다.  
(3.9도 다운 가능하지만 그냥 3.8 했다)

### 1-7. nvm을 이용한 Node.JS설치

강의에서는 Node.JS만 따로 설치한 뒤 나중에 nvm을 이용한 설치를 알려줬는데 단독 설치 부분은 그냥 강의로만 보고 nvm으로만 설치하는걸 추천한다.

nvm git(<https://github.com/nvm-sh/nvm>)  
공식 문서 내용에 따라 진행한다.

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

위 코드를 입력하면 nvm 설치 및 shell command가 추가된다.

이제 새로운 terminal을 열어서 nvm을 이용해 node를 설치해준다.  
LTS버전을 설치하는걸 추천하는데

```bash
nvm install 'lts/*'
```

라고 입력하면 lts버전 중 가장 최근 버전이 자동으로 선택되어 설치를 시작한다.  
설치된 node 목록을 보기 위해 `nvm ls`라고 입력해 현재 설치된 버전을 확인하고

```bash
nvm alias default 16.13.2(본인 버전)
```

라고 입력해 기본으로 설정할 버전을 명시해 준다.  
(하나만 설치하면 그게 기본 설정이 되어있긴 한데 나중에 다른 버전 설치 시를 대비해 그냥 설정 해주자)

### 1-8. git, github CLI 설치

강의를 보고 잘 따라하면 된다.

Github CLI(<https://github.com/cli/cli>)  
Github CLI Linux install(<https://github.com/cli/cli/blob/trunk/docs/install_linux.md>)

Github CLI Linux install공식 문서를 따라 아래 4줄을 입력하면 설치 완료.

```bash
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

Github 아이디가 없다면 만들고

```bash
git config --global user.name "<사용하고 싶은 유저명>"
git config --global user.email "<github아이디 연동된 이메일>"
```

까지 입력해 git초기 설정.

```bash
gh auth login
```

을 입력해 github아이디랑 github cli랑 연동 시켜둔다.
