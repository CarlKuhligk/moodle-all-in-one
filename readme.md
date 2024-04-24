This is a simple all-in-one Moodle image that runs with MariaDB and Nginx. Moodle is downloaded during the building of the image and only unpacked and installed when the container starts the first time. If necessary, the download path may need to be updated.

> [!NOTE]
> **`Moodle 4.3`**

> [!NOTE]
> If the app is to run on a different port, all port references must be adjusted.
>
> ```docker
> version: '3.1'
> services:
>  moodle:
>    container_name: moodle-app
>    image: moodle_all_in_one:latest
>    restart: always
>    environment:
>      TZ: Europe/Berlin
>      MOODLE_HOST: localhost
>      MOODLE_PORT: 1234 # <- here
>    ports:
>      - 1234:1234 # <- and here
>    volumes:
>      - ~:/var/lib/mysql/
> ```
