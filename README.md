# /25-02-23
## 프로젝트 생성

# /25-02-24
## 서블릿과 파일 업로드 1

### 멀티파트 사용 옵션
#### 업로드 사이즈 제한
큰파일을 무제한 업로드하게 둘 수는 없으므로 업로드 사이즈를 제한할 수 있다.
사이즈를 넘으면 SizeLimitExceededException이 발생한다.
max-file-size : 파일 하나의 최대 사이즈, 기본 1MB
max-request-size : 멀티파트 요청 하나에 여러 파일을 업로드 할 수 있는데, 그 전체 합이다. 기본 10MB

#### spring.servlet.multipart.enabled 
끄기 : spring.servlet.multipart.enable=false
켜기 : spring.servlet.multipart.enable-true (기본)
이 옵션을 켜면 스프링 부트는 서블릿 컨테이너에게 멀티파트 데이터를 처리하라고 설정한다.

# /25-02-25
## 서블릿과 파일 업로드 2

### application.properties
file.dir= 파일 업로드 경로 생성
1. 꼭 해당 경로에 실제 폴더를 미리 만들어두자
2. application.properties에서 설정할 때 마지막에 '/'(슬래시)가 포함된 것에 주의하자

### Part 주요 메서드
part.getSubmittedFileName() : 클라이언트가 전달한 파일명
part.getInputStream() : Part의 전송 데이터를 읽을 수 있다.
part.write(...) : Part를 통해 전송된 데이터를 저장할 수 있다.

서블릿이 제공하는 Part는 편하기는 하지만, HttpServletRequest를 사용해야 하고, 추가로 파일 부분만 구분하려면 여러가지 코드를 넣어야한다.


