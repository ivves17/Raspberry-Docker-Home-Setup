# [Docker setup for your rpi]
This repo has been created especially as a backup for my composes and my config files, you can use them as you like, and feel free to tell me how they have been working for you.
I've just used this setup on a rpi zero 2 W, but it should work on other Raspberry Pi models too.

## Contents
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [File Structure](#file-structure)

## Prerequisites

Things you need to have installed before starting:
* Git
* Docker

## Installation & Setup

Follow these steps to get the project running locally:

1.  **Clone the repository:**

2.  **Configure Environment Variables:**
    Create the .env files for the composes that use variables.

    **Important:** This project does not include tthe actual unbound configuration file. You must create it from the example provided.

    Ex:
    cp unbound.conf.example unbound.conf

3.  **Edit the Configuration:**
    Open `unbound.conf` and adjust the following parameters according to your network needs, for example:
    * `interface`: Change `0.0.0.0` if you need to listen on a specific IP.
    * `access-control`: Define which IPs are allowed to query the server.

4.  **Start the Composes:**
    Ex:
    * docker compose -f npm/nginxproxymg-compose.yaml up -d

## File Structure

* I strongly recommend that you use the structure below in order to avoid any problems with the volumes and the unbound config file:

```
├── .gitignore
├── README.md
├── npm
│   └── nginxproxymg-compose.yaml
├── pihole-unbound
│   ├── pihole-compose.yaml
│   └── unbound
│       └── unbound.conf.example
├── portainer
│   └── portainer-compose.yaml
└── vaultwarden
    └── vaultwarden-compose.yaml
```
