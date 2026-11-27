# cicd-infra

Інфраструктура для CI/CD практики (Jenkins + ізольовані `prod` та `test` середовища з MongoDB і API).

## Вимоги на сервері (VPS)

- Docker + Docker Compose v2
- Node.js / npm (для запуску скриптів із `package.json`)
- Git
- Відкритий порт `8080` (Jenkins), `3000` (API Prod), `3001` (API Test)

---

## Розгортання на сервері

### 1. Клонування репозиторію

Клонуй репозиторій у `/opt/cicd-infra` (шлях використовується в volume Jenkins):

```bash
cd /opt
git clone https://github.com/VitaliiShyliuk/cicd-infra.git
cd cicd-infra
```

### 2. Налаштування змінних оточення

```bash
cp .env.prod.example .env.prod
cp .env.test.example .env.test
```

### 3. Запуск середовищ

```bash
npm run deploy:prod
npm run deploy:test
```
