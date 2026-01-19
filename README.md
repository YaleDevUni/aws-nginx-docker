Dockerized Nginx Reverse Proxy (AWS)

AWS EC2에서 실행되는 Docker 기반 Nginx 리버스 프록시 설정입니다.
대용량 업로드 및 장시간 요청을 처리하도록 구성되어 있으며, 로컬 백엔드 서버와 직접 연결됩니다.



Features
	•	Nginx (Alpine)
	•	Docker / Docker Compose
	•	Reverse Proxy to 127.0.0.1:5000
	•	Max upload size: 100MB
	•	Extended proxy timeouts
	•	Host network mode



Architecture

Client -> Nginx (Docker) -> Backend (localhost:5000)



Usage
```bash
sh build.sh
```


Configuration Notes
	•	network_mode: host 사용
	•	대용량 업로드를 위해 proxy buffering 비활성화
	•	실제 클라이언트 IP 전달 지원


Requirements
	•	AWS EC2 (Linux)
	•	Docker / Docker Compose
	•	Backend service running on port 5000
