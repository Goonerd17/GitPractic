## Git 협업 규칙

### `Git Flow` 전략

- main - dev - front, back - feature_개인단위
- 깃 저장소 관리
1. 프론트 저장소 : `origin` : master / dev / feature_
2. 백 저장소 : `origin` : master / dev / feature_
3. ~~개별 저장소 : `origin` : (fork) master / dev / feature~~
- **~~개인 레포에서 작업 후 병합 순서~~**
1. 개인 작업 :
`add , commit`
로컬의 feature 브랜치에서 작업을 진행.
`git checkout dev`
dev 브랜치로 이동한다
`git merge feature`
로컬의 feature 브랜치를 dev 브랜치에 병합함

2. 팀 레포 병합 전 충돌 해결 :
`git fetch upstream`
팀 back 레포를 로컬 dev에 fetch한다.
`git merge upstream/dev`
그 후 팀 레포의 dev 브랜치를 로컬의 dev에 병합하여
발생하는 충돌을 해결한다

3. 개인 레포에 로컬 dev 브랜치를 push한다
`git push origin dev`

4. Merge Request 신청 : 깃랩
개인 레포 dev 브랜치 → 팀 back 레포 dev 브랜치에 merge request를 생성한다.

### Branch **정의** `main` `dev` `feature`

- `main`( = master) :
바로 product로 release(배포) 할 수 있는 브랜치
하나의 `main`만 사용, 배포 시 Tag 및 업데이트 내용 추가 작성, 추가 생성하지 않습니다.
- `dev` :
product로 release 할 준비가 된 가장 안정적인 브랜치로 개발이 완료된 상태라면 `main` 브랜치로 merge합니다.
하나의 `dev`만 사용, 추가 생성하지 않습니다.
- `feature` :
새로운 기능을 추가할 때 사용하는 브랜치로 `dev` 브랜치에서 분기하여 진행되며, 개발이 완료된 기능은 `dev` 브랜치로 merge합니다.
해당 feature 업무 담당자가 최신 버전의 `dev`에서 `feature/<포지션-기능명>`으로 생성합니다.

### 커밋 메시지 규칙 `Type : Subject`

- **Type**

`**feat` : 새로운 기능**

`**fix` : 버그 수정에 대한 커밋**

`**patch` : 기능 부분 코드 수정**

`refactor` : 코드 리팩토링 수정

`rm` : 기능 삭제

`docs` : 문서 수정

`style`: 스타일링 수정

- 유의미한 코드 단위/기능 완료 시에 커밋
- Reviewer, Assignee 지정

### MR 규칙 `Title` + `Description`

- TITLE : `Type : Subject`
- Description : `작업내용 작성`
- Reviewer, Assignee 지정
