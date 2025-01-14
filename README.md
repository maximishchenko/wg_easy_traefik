### Установка Docker и GIT
```shell
apt update && apt upgrade -y && apt install sudo git -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```
### Создание каталога для хранения конфигурации контейнеров
```shell
mkdir /apps && cd /apps
```

### Клонирование репозитория
```shell
git clone git@github.com:maximishchenko/wg_easy_traefik.git
```

### Перейти в каталог с проектом
```shell
cd wg_easy_traefik
```

### Скопировать шаблон параметров
```shell
cp .env.template .env
```

### Указать требуемые значения параметров в файле ```.env```

### Запустить сборку контейнеров
```shell
docker compose up -d
```

### Password hash generation

> Каждый знак ```$``` необходимо экранировать знаком ```$```, т.е. вместо одного знака необходимо каждый раз указывать 2 знака

```shell
docker run --rm -it ghcr.io/wg-easy/wg-easy wgpw 'YOUR_PASSWORD'
```