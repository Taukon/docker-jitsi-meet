
1. create .env
```shell
cp env.example .env
cp ./rtcstats-server/env.example ./rtcstats-server/.env
cp ./rtc-visualizer/env.example ./rtc-visualizer/.env
```

2. add `depends_on` to rtcstats_server and rtc_visualizer (rtcstats.yml)
```yaml
rtcstats_server:
    ...
    depends_on:
        rtcstats_initialize:
            condition: service_completed_successfully

rtc_visualizer:
    ...
    depends_on:
        rtcstats_initialize:
            condition: service_completed_successfully
```

3. run docker compose
```shell
docker-compose -f docker-compose.yml -f rtcstats.yml -f ./rtcstats/localstack/localstack.yml up -d
```