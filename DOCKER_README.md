Quick Docker guide

- Build and start services:

```bash
docker-compose up --build
```

- The frontend will be available at http://localhost (port 80).
- The backend API will be available at http://localhost:3000.
- Mongo runs internally and is preconfigured at `mongodb://mongo:27017/hiresense`.

Notes:
- Add any secret environment variables to `Backend/.env` and reference them in `docker-compose.yml` or override with your orchestration.
