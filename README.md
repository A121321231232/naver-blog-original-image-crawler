# 네이버 블로그 원본 이미지 크롤러
### 네이버 블로그의 원본 이미지를 다운로드할 수 있는 이미지 크롤러
#### 2022-10-31 업데이트
* 작은 카테고리 개별로 다운받는 대신 큰 카테고리 전체를 한 번에 다운받을 수 있도록 기능 추가
* setting.txt에 아무것도 적혀 있지 않은 상태에서 저장 경로 변경을 시도하였다가 취소했을 때 setting.txt에 현재 경로가 적히지 않도록 변경
* 게시글 주소 대신에 카테고리 주소로도 다운받을 수 있도록 기능 추가
#### 2022-08-11 업데이트
* iframe 없는 링크에서 카테고리 다운로드가 작동하지 않는 오류 수정
* 폴더를 생성할 때 양 끝의 공백을 없애지 않아 오류가 생겼던 문제 수정
* README 가독성 수정 및 내용 추가
* 카테고리 범위를 입력하기 전에 카테고리 내 게시글 갯수를 표시해 주도록 변경
* 다운로드를 할 때 링크를 여러 개 입력할 수 있도록 변경
* 사진 파일 이름이 한글로 되어 있어도 깨지지 않도록 url 디코딩을 하도록 변경
## 기능
#### 1. 다운로드 - 입력한 네이버 블로그 게시글 링크의 원본 이미지를 다운
* 사이에 띄어쓰기를 하면 여러 링크를 한 번에 입력할 수 있음(띄어쓰기는 한 칸만 해야 함)
##### 예시
     https://blog.naver.com/blogpeople/222844066273 https://blog.naver.com/blogpeople/222843909996
* 링크를 입력할 때 게시글 번호가 포함되게 입력하여야 함
##### 올바른 네이버 블로그 링크 예시
     https://blog.naver.com/blogpeople/222844066273
     https://blog.naver.com/PostView.naver?blogId=blogpeople&logNo=222844066273&categoryNo=72&parentCategoryNo=-1&viewDate=&currentPage=&postListTopCurrentPage=&isAfterWrite=true
     https://m.blog.naver.com/blogpeople/222844066273
##### 잘못된 네이버 블로그 링크 예시
     https://blog.naver.com/blogpeople
     https://blog.naver.com/PostList.naver?blogId=blogpeople&skinType=&skinId=&from=menu&userSelectMenu=true
     https://m.blog.naver.com/blogpeople
#### 2. 카테고리 다운로드 - 입력한 네이버 블로그 게시글 링크와 같은 카테고리인 모든 게시글의 원본 이미지를 다운
* 카테고리 다운로드는 링크를 여러 개 입력할 수 없음
* 큰 카테고리 내에 작은 카테고리들이 있는 경우는 작은 카테고리들 개별로만 다운로드 받을 수 있음
* 범위를 지정하여 다운로드 가능(범위를 입력하지 않으면 전부 다운)
##### 범위 입력 예시
    3 10    -3번부터 10번까지
    0 7     -처음부터 7번까지
    5 0     -5번부터 끝까지
    0 0     -전부
    2 -1    -2번부터 끝에서 1번까지
    -10 9   -끝에서 10번부터 9번까지
    -9 -2   -끝에서 9번부터 끝에서 2번까지
    
    입력하지 않고 그냥 엔터를 치면 전부 다운

#### 3. 저장 경로 변경
* 저장 경로는 setting.txt에 저장됨
* 저장 경로가 지정되어 있지 않으면 py파일 또는 exe파일이 있는 경로에 다운받음
