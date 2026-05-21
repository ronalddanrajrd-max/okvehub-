# Premium Whitelist System

Projet original inspiré des SaaS de whitelist premium : FastAPI + PostgreSQL + Redis + Discord.py + Next.js/Tailwind.

> Note : l'interface reprend une ambiance sombre/violet premium, sans copier une marque ou un service existant.

## Démarrage local
```bash
cp .env.example .env
# remplis DISCORD_* et JWT_SECRET

docker compose up --build
```

Services :
- Backend API : http://localhost:8000/docs
- Frontend : http://localhost:3000
- PostgreSQL : localhost:5432
- Redis : localhost:6379

## Railway
Crée des services séparés depuis le même repo :
- backend : root `/backend`, start `uvicorn app.main:app --host 0.0.0.0 --port $PORT`
- frontend : root `/frontend`, start `npm start`
- bot : root `/bot`, start `python main.py`
- ajoute PostgreSQL + Redis via Railway.

Railway expose `DATABASE_URL` pour Postgres. Redis peut exposer `REDIS_URL`. Railway documente l’ajout de PostgreSQL et les commandes de migration pre-deploy pour Next.js/monorepo. Voir docs Railway citées dans ma réponse.

## Commandes utiles
```bash
cd backend && alembic upgrade head
cd frontend && npm run dev
cd bot && python main.py
```
