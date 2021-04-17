#


# docker + rails6 + postgresql

## 手順

```console

cd railsapp
docker-compose run web rails new . --force --no-deps --database=postgresql --skip-bundle

cd ..
cp database.yml-sample railsapp/config/database.yml

docker-compose build
docker-compose run web bundle install
docker-compose run web rails db:create
docker-compose run web rails webpacker:install
docker-compose up -d
```

