sa-smarthome-ivideon
====================

[![Build Status](https://travis-ci.org/softasap/sa-smarthome-ivideon.svg?branch=master)](https://travis-ci.org/softasap/sa-smarthome-ivideon)


Example of usage (all parameters are optional)

Simple
```YAML
  roles:
    - {
        role: "sa-smarthome-ivideon"
      }
```

Advanced:

```YAML
  roles:
    - {
        role: "sa-smarthome-ivideon"
      }
```



==================================


Для установки версии IvideonServer без графического интерфейса (для Linux-серверов) требуется установить отдельно пакет ivideon-server-headless или camera-server-headless:

 sudo apt-get install ivideon-server-headless

Далее необходимо провести настройку сервера с графическим интерфейсом на отдельной машине, затем скопировать файл конфигурации сервера videoserverd.config в директорию /home/<имя пользователя>/.IvideonServer/videoserverd.config

Если необходимо вести запись локального архива, то необходимо изменить путь к архиву в перенесенном файле конфигурации:

"path" : "/home/<имя пользователя>/.IvideonServer/archive"

Привязка сервера к аккаунту производится следующей командой:

/opt/ivideon/ivideon-server/videoserver --config-filename=/path/to/videoserverd.config --attach --email="account@ivideon.com" --server-name="My First Server"

Для автоматического запуска сервера при старте системы необходимо выполнить следующее:

sudo /opt/ivideon/ivideon-server/init_ctl install <имя пользователя> <путь к файлу конфигурации>

Для удаления его из автозапуска:
sudo /opt/ivideon/ivideon-server/init_ctl uninstall

Для управления видеосервером необходимо использовать скрипт init.d:
/etc/init.d/videoserver <start|stop|restart|status>
