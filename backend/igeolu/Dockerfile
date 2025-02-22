FROM openjdk:17-jdk-slim

ARG JAR_FILE=build/libs/*.jar
# jar 파일 복제
COPY ${JAR_FILE} app.jar

ENV TZ=Asia/Seoul \
    LANG=ko_KR.UTF-8

# prod 모드 실행 명령어
# ENTRYPOINT ["java", "-Dspring.profiles.active=prod", "-jar", "app.jar"]

# 기본 명령어
# ENTRYPOINT ["java", "-jar", "/app.jar"]

# 메모리 모니터링 추가
ENTRYPOINT ["java", "-Dspring.profiles.active=prod",
     "-Dcom.sun.management.jmxremote=true",
     "-Dcom.sun.management.jmxremote.local.only=false",
     "-Dcom.sun.management.jmxremote.port=1099",
     "-Dcom.sun.management.jmxremote.ssl=false",
     "-Djava.rmi.server.hostname=i12d205.p.ssafy.io",
     "-Dcom.sun.management.jmxremote.rmi.port=1099",
     "-Dcom.sun.management.jmxremote.authenticate=false",
     "-jar", "app.jar"]