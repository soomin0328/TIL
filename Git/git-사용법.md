## git 사용법


```git
# 사용자 정보 설정
git config --global user.name "user name"
git config --global user.email "user email"


# 새로운 저장소 만들기.
# 저장소 전용 폴더를 만들고 그 안에서 명령어 실행.
# .git 폴더 생성됨.
git init


# 저장소 받아오기
# 로컬 저장소 clone
git clone /로컬/저장소/경로
# 원격 서버 저장소 clone
git clone 사용자명@호스트:원격/저장소/경로


# git 변경사항 확인
git status


# 현재 연결된 원격 저장소 확인
git remote -v


# 로컬 저장소를 원격 저장소에 맞춰 갱신
git pull


# index에 추가
# 특정 파일 추가
git add <파일 이름>
# 해당 폴더의 전체 파일 추가
git add *


# commit log 확인
git log


# commit
git commit -m "커밋 메세지"


# 직전에 작성한 commit 메세지 수정
git commit --amend


# 파일 add & commit 동시에
git commit -am "커밋 메세지"


# push
git push origin master(branch 이름)


# branch 조회
git branch


# branch 생성과 동시에 바꾸기
git checkout -b <branch명>


# master로 돌아오기
git checkout master


# branch 이름 변경
git branch -m <원래 폴더> <바꿀 이름>


# branch 삭제
git branch -d <branch명>


# branch push
git push origin <branch명>


# 다른 branch의 변경 내용을 현재 branch에 merge
git merge <branch명>


# merge전, branch 변경 사항 비교
git diff <원래 branch> <비교 대상 branch>


# 로컬 변경 내용 되돌리기(이미 인덱스에 추가된 내용과 새로 생성한 파일은 그대로 남음)
git checkout -- <파일 이름>


# 로컬에 있는 모든 변경 내용 포기하고 원격 저장소의 최신 이력 가져오기
git fetch origin
git reset --hard origin/master
```