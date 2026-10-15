# Folder and file structure

This explains the project folder and file structure.

## Content

1. [Folder structure](#folder-structure)
2. [File naming convention](#file-naming-convention)

## Folder structure

The project is structured as a monolith. Meaning there is only on big `api` app folder instead of being split into 
feature apps.

The following is a list of all relevant files and folders for developing a feature in the astra-service project.

```
🗀 api
├── 🗀 access_policy     - contains access policies and permission definitions
├── 🗀 authentication    - contains all auhtentication definitions used by the api
├── 🗀 management        - contains management commands for cli interactions
├── 🗀 migrations        - contains all migration instruction definitions for the databse
├── 🗀 models            - contains all data model definitions
├── 🗀 serializers       - contains all serializers
├── 🗀 services          - contains secific service helpers
├── 🗀 utils             - contains general helpers
├── 🗀 views             - contains view definitions
├── admin.py            - contains all admin view definitions
├── settings.py         - contains static and dynamic (environment variables) settings
└── urls.py             - contains all url patterns and router registrations
```

To generate migration the `makemigration` command is used. For example:

```bash
python manage.py makemigrations
```

Official django [migration docs](https://docs.djangoproject.com/en/6.1/topics/migrations/)

## File naming convention

Prefix: `<feature name>`

Suffix: `<content type>`

Example: `blackboard_post_model.py` → Prefix: `blackboard` (Feature Name), Suffix: `model` (Type)