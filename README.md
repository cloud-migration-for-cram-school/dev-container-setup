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

#### docker

To configure the index files, modify the `Dockerfile` file located in `docker/python`.

```Dockerfile
CMD ["uvicorn", "<project.py>:app", "--host", "0.0.0.0", "--port", "8000"]
```

### Backend

Please ensure that the environment variable file (`.env`) strictly follows Linux syntax. Create a `config` folder at the root level of the `backend` directory and store the API key there.

#### Incorrect Example

```plaintext
.env
MAPPING_FILE = backend\service\mapping.json
API_PATH = \app\backend\config\api.json
FOLDER_ID = ****************
```

#### Correct Example

```plaintext
.env
MAPPING_FILE = backend/service/mapping.json
API_PATH = /app/backend/config/api.json
FOLDER_ID = ****************
```

#### Additional Notes

- **Environment variable syntax:** Ensure that file paths use forward slashes (`/`), as is standard in Linux-based environments (including Docker containers). Avoid using backslashes (`\`), which are used in Windows paths.
- **File locations:** The `MAPPING_FILE` and `API_PATH` should be relative to the application’s internal directory structure when running in a Docker container or Linux environment.
- **API Key Storage:** Store the API key in the `config` directory, which should be created at the root of the `backend` folder. This keeps sensitive information separated from the rest of the codebase, ensuring better security practices.

### Summary

- **Paths must follow Linux conventions** with forward slashes `/`.
- **Ensure proper file organization** by storing the API key and other sensitive files in the appropriate `config` directory.
