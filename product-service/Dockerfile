# 사용할 베이스 이미지를 지정
FROM python:3.9-slim-bullseye

# 작업 디렉토리 설정
WORKDIR /app

# 의존성 파일을 컨테이너로 복사
COPY ./api/requirements.txt /app/requirements.txt

# 의존성 설치
RUN pip install --no-cache-dir -r /app/requirements.txt

# 현재 디렉토리의 모든 파일을 컨테이너의 작업 디렉토리로 복사
COPY ./api /app/api

ENV PYTHONPATH=/app

EXPOSE 8000

VOLUME /api/products.db

# 컨테이너가 시작될 때 실행될 명령어
# CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
CMD ["python", "api/main.py"]

