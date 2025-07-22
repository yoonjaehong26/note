0.기본세팅 

homebrew설치
//Brew install git

git config --global init.defaultBranch main
기본 브랜치 이름을 master에서 main으로 바꿔주는 것

git config --global core.editor "code --wait"
이거 입력하면 git의 기본 에디터가 Vim 말고 VSCode로 변경됩니다

git config --global user.email “a287933@naver.com”
git config --global user.name “윤재홍”
처음 컴퓨터 사용 시 아이디,비번 등록








1.코드 로컬저장소에 저장 

1. git init 
//이 폴더를 감시하기 시작함, 로컬 repository저장

2. git add 파일1 파일2 파일3                              // git add .
    git commit -m ‘메모내용’ 						
	


 

git restore --staged 파일명		//스태이징 된거 취소

<img width="1226" height="323" alt="Image" src="https://github.com/user-attachments/assets/55932dff-5698-402c-9dbe-92badc4a2444" />
￼



2. 로그확인
Git status
git log --all --oneline —graph		//근데 그냥 옆애 있음  extension에서 Git graph설치







3.브랜치 만들기,이동



git branch 브랜치명				//브랜치 생성

git switch 브랜치명.             			//브랜치 이동







3-1.merge(합치기)

Git switch main.        //매인브랜치로 이동
Git merge backup1       //합치고싶은 브런치 입력. 겹치는 코드 일단 다 표시해주니 지우면 됨




3-2 Branch 지우기

git branch -d 브랜치이름			//쓴거
git branch -D 브랜치이름			//안쓴거





5 git 로그 깔끔하게 하는 법

(1)rebase
￼<img width="1430" height="863" alt="Image" src="https://github.com/user-attachments/assets/3de1ba36-9515-41d5-91dc-4a32ec88d9ae" />

git switch 새로운브랜치
git rebase main				//시작점을 메인에 이어붙임

git switch main
git merge 새로운브랜치.  	//메인에 가지를 붙임

=>한줄로 가능





(2)squash

git switch main

git merge --squash 브랜치명		//브런치 갈아버리기
git commit -m '메세지'

￼<img width="1430" height="863" alt="Image" src="https://github.com/user-attachments/assets/3de1ba36-9515-41d5-91dc-4a32ec88d9ae" />








6. 돌아가기
git restore --source 커밋아이디 파일명.  		//그 아이디의 커밋한 시점으로 돌아가기


7.지우기
git revert 커밋아이디						//그 아이디의 커밋한 부분 없앤 커밋 생성


*주의*리셋
git reset --hard 커밋아이디			//로그까지 다 지우고 그아이디의 커밋으로 돌아감










1. Git에 저장소 백업하기

//(1)git branch -M main					//혹기 모르니 main branch 이름 main으로 설정 권고

(2)git push -u 원격저장소주소 브랜치명 			//저장소 올리기(올리기 전commit 해야함)
 
(3)git push												//-U는 뒤에 주소 저장,처음한번만 쓰면 됨
 









협업
1. git clone 저장소주소                 //내 vsc에 인터넷의 코드 브런치 다운받아 옴 

2. Git에서 공동작업자여야만 함

3. 근데 온라인에서 변경된 내용 있으면 push가 안됨 따라서 최근상태의 코드 다운받아야함
: git pull 원격저장소주소 브랜치명


온라인 브랜치
1. 그냥 깃헙페이지에서 가능
2. (1)git push 원격저장소주소 로컬브랜치명.              으로 로컬 브런치 올림
    3. 깃헙 fullrequest버튼에서 하면 임시 저장 가능,토론,리뷰가능 해보면 암




