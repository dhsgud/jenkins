# CLI를 이용한 Jenkins 임의 파일 읽기 취약점(CVE-2024-23897)


Jenkins는 오픈소스로 지속적 통합 서비스를 제공하는 도구입니다.(자동화 서버)입니다.
Jenkins에서는 [args4j library](https://github.com/kohsuke/args4j)를 사용하여 CLI 명령을 처리할 때 Jenkins 컨트롤러의 명령 인수와 옵션을 구문 분석합니다. 
이 명령 구문 분석기 @에는 인수의 문자와 파일 경로를 파일 내용(expandAtFiles)로 바꾸는 기능이 있어 공격자가 Jenkins 서버에서 임의의 파일을 읽도록 유도합니다.

Jenkins 버전은 2.441 이고 이전 버전에 모두 영향을 미칩니다.

참고 자료 :
- <https://github.com/vulhub/vulhub/tree/master/jenkins/CVE-2024-23897>
- <https://www.jenkins.io/security/advisory/2024-01-24/#SECURITY-3314>
- <https://mp.weixin.qq.com/s/2a4NXRkrXBDhcL9gZ3XQyw>

## 취약한 환경 시작
docker-compose.yml 가 존재하는 디렉토리에서

```
docker compose up -d
```

![](1.png)

## 익스플로잇


![](1.png)
