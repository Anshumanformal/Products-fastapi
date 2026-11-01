docker ps -a
docker exec -it python-3.11 bash
source /app/myenv/bin/activate


docker-compose up -d --force-recreate
docker-compose logs --tail=100 python

docker compose restart

<!-- To start the server -->
<!-- uvicorn main:app --reload -->
uvicorn main:app --host 0.0.0.0 --port 8000 --reload

pip install -r requirements.txt