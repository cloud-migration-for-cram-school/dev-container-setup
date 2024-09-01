# dev-container-setup

## How to Use

This guide is for your personal use to help you remember how to set up and run the project. If you need the environment file and folder, please contact me.

### Commands

#### Docker

- **Launch Docker:** `docker-compose up -d --build`
- **Stop Docker:** `docker-compose down`

## Adding some Files

Please clone frontend and backend as is.

### structure

```bash
project-root/
│
├── docker/
│   ├── python/
│   │   └── Dockerfile            # Dockerfile for the Python backend
│   ├── nginx/
│   │   └── default.conf          # Nginx configuration file
│
├── backend/
│   ├── app.py                    # Main backend application file
│   ├── requirements.txt          # Python dependencies
│   └── Other files related to the backend
│
├── frontend/
│   ├── src/
│   │   ├── index.tsx             # Main frontend entry point
│   │   └── Other frontend source files
│   ├── package.json              # Node.js dependencies for the frontend
│   └── vite.config.ts            # Vite configuration file
│
├── docker-compose.yml            # Docker Compose configuration
├── .env                          # Environment variables file
├── .gitignore                    # Git ignore rules
├── README.md                     # Project documentation (this file)
└── Other files

```

### Necessary Settings

To configure the index files, modify the `Dockerfile` file located in `docker/python`.

```Dockerfile
CMD ["uvicorn", "<project.py>:app", "--host", "0.0.0.0", "--port", "8000"]
```
