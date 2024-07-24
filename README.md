---

Русский

---

Описание

Этот PowerShell скрипт обеспечивает функции для резервного копирования (бэкапа) и восстановления данных приложений. Он может обрабатывать как абсолютные, так и относительные пути, а также поддерживает переменные окружения для указания путей.

Предварительные требования

- PowerShell 5.1 или более поздняя версия.
- Windows операционная система.

Настройка

1. Создайте файл конфигурации backup_config.json в той же директории, что и скрипт. Пример конфигурационного файла:
```json
[
    {
        "appName": "App1",
        "backupItems": [
            "%USERPROFILE%\\Documents\\App1\\Folder1",
            "%USERPROFILE%\\Documents\\App1\\file1.txt"
        ]
    },
    {
        "appName": "App2",
        "backupItems": [
            "C:\\Path\\To\\App2\\Folder2",
            ".\\localfolder\\file2.jpg"
        ]
    }
]
```

2. Сохраните скрипт в той же директории с именем backup_script.ps1.

Использование

Бэкап данных

Для выполнения операции бэкапа:

.\backup_script.ps1 -Operation backup


Восстановление данных

Для восстановления последнего бэкапа для всех приложений:

.\backup_script.ps1 -Operation restore


Для восстановления определенного бэкапа по метке времени для конкретного приложения:

.\backup_script.ps1 -Operation restore -Timestamp "20230101123045" -AppName "App1"


Команды

- -Operation backup: Запускает операцию бэкапа для всех приложений, указанных в конфигурационном файле.
- -Operation restore: Запускает операцию восстановления. Если указаны -Timestamp и -AppName, скрипт восстановит указанное приложение до указанной метки времени.
- -Timestamp: (Опционально) Указывает метку времени для восстановления конкретного бэкапа.
- -AppName: (Опционально) Указывает имя приложения для восстановления.

---

English

---

Description

This PowerShell script provides functions for backing up (backup) and restoring application data. It can handle both absolute and relative paths and supports environment variables for specifying paths.

Prerequisites

- PowerShell 5.1 or later.
- Windows operating system.

Setup

1. Create a configuration file named backup_config.json in the same directory as the script. Example configuration file:
```json
[
    {
        "appName": "App1",
        "backupItems": [
            "%USERPROFILE%\\Documents\\App1\\Folder1",
            "%USERPROFILE%\\Documents\\App1\\file1.txt"
        ]
    },
    {
        "appName": "App2",
        "backupItems": [
            "C:\\Path\\To\\App2\\Folder2",
            ".\\localfolder\\file2.jpg"
        ]
    }
]
```

2. Save the script in the same directory with the name backup_script.ps1.

Usage

Backup Data

To perform a backup operation:

.\backup_script.ps1 -Operation backup


Restore Data

To restore the latest backup for all applications:

.\backup_script.ps1 -Operation restore


To restore a specific backup by timestamp for a particular application:

.\backup_script.ps1 -Operation restore -Timestamp "20230101123045" -AppName "App1"


Commands

- -Operation backup: Initiates the backup operation for all applications specified in the configuration file.
- -Operation restore: Initiates the restore operation. If -Timestamp and -AppName are specified, the script will restore the specified application to the specified timestamp.
- -Timestamp: (Optional) Specifies the timestamp for restoring a particular backup.
- -AppName: (Optional) Specifies the name of the application to restore.
