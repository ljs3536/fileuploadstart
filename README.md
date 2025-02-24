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
