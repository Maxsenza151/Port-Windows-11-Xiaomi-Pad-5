﻿<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Установка Windows на Xiaomi Pad 5

## Решение возможных проблем


## Устройство запускается в Android, но не запускается в загрузчик

### Требования:

- [ADB и Fastboot](https://developer.android.com/studio/releases/platform-tools)

> **Внимание** Возможно, эти шаги не помогут потому на что Xiaomi Pad 5 нет полностью рабочего рекавери для установки. Также как и у большинства современных A/B устройств у нас нет установщика TWRP из-за изменённого загрузчика. Если у вас установлена AOSP прошивка, возможно она содержит предустановленное AOSP рекавери. Вы можете использовать его для шагов ниже. Если у вас установлена MIUI без Root-доступа, эти шаги вам не помогут.

> Также, пожалуйста, избегайте имён разделов, которые содержат пробелы и специальные символы, и, если это возможно, используйте имена `ESPNABU` и `WINNABU`, которые проверены уже сотни раз. Если вы испортите загрузчик запрещёнными выше именами разделов и у вас MIUI без Root-доступа, вам необходимо прошить прошивку в режиме EDL с авторизованным аккаунтом, что может привести к денежным тратам.


Ошибка связана с тем, что загрузчик не может обработать имена разделов. Чтобы это исправить:

- Запустите рекавери

- Подключите планшет к ПК

- На компьютере откройте командную строку

- Выполните ```adb shell```

- Выполните ```parted```

- Выполните ```print``` чтобы получить список разделов

- Найдите разделы, содержащие пробелы или специальные символы, например "Basic Data Partition" и запомните их номера

- Теперь выполните ```rm <vol number>```, например ```rm 99```


## BSOD ошибка "fsa4480.sys" при загрузке

- Откройте на компьютере папку с драйверами

- Удалите папку ```components\QC8150\Device\DEVICE.SOC_QC8150.NABU\Drivers\USB```

- Переустановите драйверы

- Запустите UEFI

- После запуска верните папку с драйвером и переустановите драйверы снова

