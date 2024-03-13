<h1>ЛБ по облачным технологиям</h1>

## 1.Получения ssh-ключа: <br>
Заходим в консоль и прописываем - `ssh-keygen` <br>
После проходим по пути: `<Диск>:\Users\<ваша-учетка>\.ssh\id_rsa.pub` <br>
## 2.Опубликовать приложение через взиул студио: <br>
## 3.Подключение к облачной машины: <br> 
Заходим в консоль и прописываем `ssh <user>@<ваш публичный ssh-ключ>` <br>

## 4.Настройка облачной машины: <br>
[Я следовал по документации](https://docs.docker.com/engine/install/ubuntu/) <br>
<br>
`sudo apt-get update` <br> 
`sudo install -m 0755 -d /etc/apt/keyrings` <br>
`sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc` <br>
`sudo chmod a+r /etc/apt/keyrings/docker.asc` <br>

`echo \` <br> 
`"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \` <br>
`$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \` <br>
`sudo tee /etc/apt/sources.list.d/docker.list > /dev/null` <br>
## 5.Установка Docker'а <br>

`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-pluginte`<br>
`sudo docker run hello-world` - проверка докера и создания hello-world <br>

## 6.Установка .NET приложения в докер Docker'а <br>
Заходим в докер прописывая - `sudo docker login`. Далее прописываем логин и пароль <br> 
Далее прописываем - `sudo docker pull <ваш логин>/<название репозитория>` / если выходит ошибка прописываем - `sudo docker pull <ваш логин>/<название репозитория>:<контейнер>` <br>
Далее прописываем - `sudo docker run -p 80:5000 -d --rm --name <название контейнера в приложении докера> <ваш логин>/<название репозитория>` <br>
Ура! Наше приложение загрузилось в докер. <br>


