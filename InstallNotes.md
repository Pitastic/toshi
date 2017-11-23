In `docker-compose.yml` ggf. die Variablen im Container `web` ändern:

```
- DATABASE_URL=postgres://postgres:@db:5432
- REDIS_URL=redis://redis:6379
```

und folgende Zeile auskommentieren:

```
command: bundle exec puma
```

Dafür den `web` Conatiner starten und betreten und folgende Kommandos händisch ausführen:

```
bundle exec rake db:migrate
foreman start # dies ggf. von außerhalb des Containers
```

Alle Container runterfahren und wieder starten (in Reihenfolge).


Angelehnt an:
http://www.soroushjp.com/2014/10/15/deploying-your-own-toshi-api-bitcoin-node-using-coreos-docker-aws/
