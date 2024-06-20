# django-youtube-restapi

Docker: 애플리케이션을 컨테이너화하여 개발, 배포 및 실행하는 플랫폼.
Docker 구성요소: Docker 엔진, Docker 이미지, Docker 컨테이너.
Docker 이미지: 애플리케이션 실행을 위한 파일과 설정을 포함한 읽기 전용 템플릿.
Docker 컨테이너: Docker 이미지를 기반으로 생성되며, 실행 중인 애플리케이션과 그 의존성을 담고 있는 격리된 환경.
CI/CD: 지속적인 통합과 배포를 통해 코드 변경 사항을 자동으로 빌드, 테스트, 배포하는 프로세스
GitHub Actions: GitHub에서 제공하는 자동화 도구로, CI/CD 파이프라인을 쉽게 설정하고 관리할 수 있게 해준다
PostgreSQL의 장점: ACID 준수, 강력한 확장성, 다양한 데이터 타입 지원, 고급 쿼리 최적화, 오픈 소스.

(1) User
- email
- password
- nickname
- is_business

(2) Video
- title
- description
- link
- views_count
- thumbnail
- video_file: link
- User: FK

ex) 파일(이미지, 동영상)
=> 장고에 부하가 걸림.
=> S3 Bucket(저렴, 속도가 빠름) -> 결과물: 링크

(3) Reaction
- User: FK
- Video: FK
- reaction (like, dislike, cancel) => 실제 youtube rest api

(4) Comment
- User: FK
- Video: FK
- content
- like
- dislike

(5) Subscription
- User: FK => subscriber (내가 구독한 사람)
- User: FK => subscribed_to (나를 구독한 사람)

(6) Common
- created_at
- updated_at