
# Ansible Playbook for Deploying FastAPI Boilerplate with PostgreSQL and Nginx

This repository contains an Ansible playbook to deploy a FastAPI application with PostgreSQL and Nginx on a local server. The playbook handles the creation of necessary users, directory setup, package installations, PostgreSQL configuration, and running the FastAPI application.

## Prerequisites

- Ansible installed on your local machine.
- A Unix-like operating system (e.g., Ubuntu).
- Basic knowledge of Ansible and YAML syntax.

## Playbook Overview

The playbook performs the following tasks:
1. Creates a user `hng` with sudo privileges.
2. Clones the FastAPI boilerplate repository.
3. Installs necessary system and Python packages.
4. Configures and starts PostgreSQL with a specific user and database.
5. Sets up RabbitMQ.
6. Configures and starts Nginx as a reverse proxy for the FastAPI application.
7. Configures logging for the FastAPI application.

## Variables

- `postgres_password`: Password for the PostgreSQL `postgres` user.
- `db_name`: Name of the PostgreSQL database to be created.
- `db_user`: Username for the PostgreSQL database.
- `db_password`: Password for the PostgreSQL database user.

## Playbook Tasks

### User and Directory Setup

1. **Create `hng` user with sudo privileges**
   - Ensures the `hng` user is created with sudo privileges and a home directory.
2. **Set `hng` user password**
   - Sets the password for the `hng` user.
3. **Create and set permissions for /opt/stage_5b directory**
   - Creates the directory `/opt/stage_5b` and sets ownership to the `hng` user.
4. **Mark /opt/stage_5b as a safe directory for Git**
Here's a detailed `README.md` file for the Ansible playbook based on the latest modifications:

```markdown
# Ansible Playbook for Deploying FastAPI Boilerplate with PostgreSQL and Nginx

This repository contains an Ansible playbook to deploy a FastAPI application with PostgreSQL and Nginx on a local server. The playbook handles the creation of necessary users, directory setup, package installations, PostgreSQL configuration, and running the FastAPI application.

## Prerequisites

- Ansible installed on your local machine.
- A Unix-like operating system (e.g., Ubuntu).
- Basic knowledge of Ansible and YAML syntax.

## Playbook Overview

The playbook performs the following tasks:
1. Creates a user `hng` with sudo privileges.
2. Clones the FastAPI boilerplate repository.
3. Installs necessary system and Python packages.
4. Configures and starts PostgreSQL with a specific user and database.
5. Sets up RabbitMQ.
6. Configures and starts Nginx as a reverse proxy for the FastAPI application.
7. Configures logging for the FastAPI application.

## Variables

- `postgres_password`: Password for the PostgreSQL `postgres` user.
- `db_name`: Name of the PostgreSQL database to be created.
- `db_user`: Username for the PostgreSQL database.
- `db_password`: Password for the PostgreSQL database user.

## File Structure

```
ansible_project/
│
├── main.yaml                 # Main playbook file
├── README.md                 # This README file
└── requirements.txt          # Python package requirements for FastAPI application
```

## Playbook Tasks

### User and Directory Setup

1. **Create `hng` user with sudo privileges**
   - Ensures the `hng` user is created with sudo privileges and a home directory.
2. **Set `hng` user password**
   - Sets the password for the `hng` user.
3. **Create and set permissions for /opt/stage_5b directory**
   - Creates the directory `/opt/stage_5b` and sets ownership to the `hng` user.
4. **Mark /opt/stage_5b as a safe directory for Git**
   - Configures Git to treat `/opt/stage_5b` as a safe directory.
5. **Clone the FastAPI boilerplate repository**
   - Clones the repository into `/opt/stage_5b` as the `hng` user.

### Package Installation

6. **Update and install system dependencies**
   - Installs necessary system packages including `python3-pip`, `postgresql`, `nginx`, and `python3-venv`.
7. **Install required Python packages**
   - Installs Python packages specified in `requirements.txt`.

### PostgreSQL Configuration

8. **Ensure PostgreSQL is running**
   - Starts and enables PostgreSQL service.
9. **Print pg_hba.conf content before modification**
   - Prints the initial content of `pg_hba.conf` for debugging.
10. **Modify PostgreSQL authentication method**
    - Removes any existing `md5` authentication lines and adds the new method.
11. **Print pg_hba.conf content after modification**
    - Prints the modified content of `pg_hba.conf` for debugging.
12. **Reload and restart PostgreSQL**
    - Reloads and restarts PostgreSQL to apply changes.
13. **Set PostgreSQL password for `postgres` user**
    - Sets the password for the `postgres` user.
14. **Create PostgreSQL database and user**
    - Creates the specified database and user, and grants necessary privileges.

### Application Setup

15. **Create .env.local file with database credentials**
    - Creates `.env.local` file with database credentials in `/opt/stage_5b`.
16. **Install RabbitMQ**
    - Installs and starts RabbitMQ service.
17. **Create a Python virtual environment**
    - Creates a virtual environment for the application.
