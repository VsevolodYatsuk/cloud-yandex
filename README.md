<h1>ЛБ по облачным технологиям</h1>

## 1.Получения ssh-ключа: <br>
Заходим в консоль и прописываем - `ssh-keygen`
После проходим по пути: `Диск:\Users\<ваша-учетка>\.ssh\id_rsa.pub`
## 2.Подключение к облачной машины: <br>
Заходим в консоль и прописываем `ssh user@hostname`

## 3.Настройка облачной машины: <br>
[Я следовал по документации](https://docs.docker.com/engine/install/ubuntu/)
`sudo apt-get update`
`sudo install -m 0755 -d /etc/apt/keyrings`
`sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc`
`sudo chmod a+r /etc/apt/keyrings/docker.asc`

`echo \`
`"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \`
`$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \`
`sudo tee /etc/apt/sources.list.d/docker.list > /dev/null` <br>
## 4.Установка Docker'а <br>

`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-pluginte`
`sudo docker run hello-world` - проверка докера и создания hello-world

## 5.Установка .NET приложения в докер Docker'а <br>
Заходим в докер прописывая - `sudo docker login`. Далее прописываем логин и пароль
Далее прописываем - `sudo docker pull <ваш логин>/<название репозитория>` / если выходит ошибка прописываем - `sudo docker pull <ваш логин>/<название репозитория>:<контейнер>`
Далее прописываем - `sudo docker run -p 80:5000 -d --rm --name <название контейнера в приложении докера> <ваш логин>/<название репозитория>`


