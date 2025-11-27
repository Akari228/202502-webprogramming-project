# 202502-webprogramming-project
프로젝트 히스토리 작성

# 2025 / 11 / 20
## 이동욱 작성
가장 최신 버전 업로드 완료 했습니다.

1. 압축 파일 해체
2. 새로운 가상환경 생성 : python -m venv venv
3. 가상환경 진입(activate 실행)
4. pip install -r requirements.txt 입력 (좀 오래걸림)

이 부분 다시 한번 진행하시면 됩니다.

이제부터 여기에 파일 업로드 하겠습니다. 업로드 하실 파일은 작업하면서 수정된 파일들( EX)urls.py, index.html, study-detail.html ) 만 업로드 해주시고
여기 README.md 에 히스토리까지 작성해주시면 감사하겠습니다.

# 2025 / 11 / 21

# 2025 / 11 / 22
## 김강현 작성
오늘 스터디 그룹 관련 편의 기능과 게시판 상세 보기/댓글 기능을 추가했습니다. 수정 또는 추가한 파일이 한두개가 아니라서 그냥 압축 폴더(update_kang.zip)로 올립니다. 설정 방법은 동욱씨가 설명했으니 생략하고 혹시나 팀원분들의 데이터베이스에 아직 '댓글(Comment)' 테이블이 없어 no such table: study_comment" 오류가 뜰 가능성이 있으니 python manage.py runserver를 하기 전에 터미널에 python manage.py migrate를 먼저 한번 실행해주세요.

아래는 자세한 수정사항입니다.

1. 스터디 정보 수정 기능 (리더 전용)
내용: 스터디 상세 화면에서 리더에게만 보이는 '✏️ 수정하기' 버튼(빨간색 테두리)을 추가했습니다. 버튼을 누르면 그룹명, 소개, 요일 등을 수정할 수 있습니다.

수정한 파일: study/views.py, study/urls.py, study/templates/study-detail.html

추가한 파일: study/templates/edit_study.html

2. 스터디 입장 버튼 개선
내용: 내가 참여한 그룹일 경우, 기존의 비활성화된 "이미 참여중인 스터디입니다" 버튼을 삭제하고, 클릭 시 바로 게시판으로 이동하는 "스터디 입장 →" 버튼(초록 배경/초록 테두리)으로 교체했습니다.

수정한 파일: study/templates/study-detail.html

3. 게시판 화면 네비게이션 변경
내용: 게시판(스터디 내부) 화면 왼쪽 위의 "← 내 스터디 목록으로 돌아가기" 링크를 "← 홈으로 돌아가기"로 변경하여 동선을 단축했습니다.

수정한 파일: study/templates/study-joined.html

4. 글쓰기 게시판 종류 자동 선택
내용: 공지사항/자료실/자유게시판 각 섹션의 '+ 새 글 쓰기' 버튼을 누르면, 글쓰기 화면에서 해당 게시판 종류가 자동으로 선택되어 있도록 개선했습니다.

수정한 파일: study/templates/study-joined.html, study/views.py, study/templates/create-post.html

5. 게시글 상세 보기 및 댓글 기능 (★중요★)
내용:

게시글 제목 클릭 시 상세 내용을 볼 수 있는 페이지를 만들었습니다.

댓글 작성, 수정, 삭제 기능을 구현했습니다.

기존에 TIME_ZONE = 'UTC' 로 설정되어 있던걸 TIME_ZONE = 'Asia/Seoul'로 변경해 한국과 약 9시간정도 차이가 나던 문제를 해결했습니다.

상세 페이지 디자인(글자 크기 확대, 게시판 아이콘 표시 등)을 개선했습니다.

수정한 파일: study/models.py (Comment 모델 추가), study/views.py, study/urls.py, study/templates/study-joined.html, config/settings.py

추가한 파일: study/templates/post_detail.html, study/templates/edit_comment.html

# 2025 / 11 / 23
## 이동욱 작성

1. 파일 업로드 추가

스터디 그룹 게시판에서 파일 업로드를 할 수 있습니다.

3. 그룹 생성하기 페이지 뒤로가기 버튼 추가

뒤로가기 버튼 없던거 추가

그리고 파일 옮기셨다면, 가상 환경 상태에서 터미널에

python manage.py makemigrations

python manage.py migrate

이 두개 명령어 꼭 입력해주세요!

수정된 파일은 update_LEE 이거로 업로드 해놓았습니다. 그거 그대로 가져다가 쓰시면 됩니다.

# 2025 / 11 / 24

수정됨


# 2025 / 11 / 25

## 최진우 작성
수정 파일 제가 올려놨습니다.
WP_jinu_Beta.zip입니다.

## 이동욱 작성
추가로 오류 수정 했습니다. 11.25_update 파일 다운 받으시면 study-datail.html 과 search.html 파일 두 개 있습니다. 이거 두개 덮어쓰기 하면 적용 됩니다.

현재 진행 사항까지 최종 업데이트 해놓앗습니다. yonsei(11.25).zip
venv를 제외한 전체파일이라서 이거도 그냥 덮어쓰거나 아니면 venv 파일만 가져오시면 바로 사용 가능하실겁니다.

# 2025 / 11 / 26
## 최진우 작성
년도 안넘어가던거 수정해놨습니다. views.py 날짜 로직에 내년 로직이 없었네요. 제가 수정해서 11_26.zip 올려놨습니다.
전체파일입니다.

## 이동욱 작성
년도 수정

일정 내용 수정 및 삭제 추가

게시글 내용 수정 및 삭제 추가

전체 파일 yonsei.zip 업로드 완료 (최신 버전 업데이트)

수정된 파일만 확인하고 싶다면 11.26_update.zip 확인

# 2025 / 11 / 27

최종본 업로드 해놓았습니다. yonsei.zip 다운로드해서 적용바랍니다.

⚠️ 중요: 모델을 수정했으니 터미널에 꼭 입력하세요!(가상환경에서)

1. python manage.py makemigrations

2. python manage.py migrate

수정사항 : 일정 내용 key 값 추가(작성한 사람만 수정/삭제 가능), 게시판 대댓글 기능 추가

# 2025 / 11 / 28

# 2025 / 11 / 29
