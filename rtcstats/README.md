1. Create `.env`
```shell
cp env.example .env
cp ./rtcstats-server/env.example ./rtcstats-server/.env
cp ./rtc-visualizer/env.example ./rtc-visualizer/.env
```

2. Edit `rtc-visualizer/.data/users.json`
```json
{
    "Alice": "XXX",
    "Bob": "YYY"
}
```

3. Run docker compose
```shell
docker-compose -f docker-compose.yml -f rtcstats.yml up -d
```
---
Run docker compose using localstack
```shell
docker-compose -f docker-compose.yml -f rtcstats.yml -f ./rtcstats/localstack/localstack.yml up -d
```