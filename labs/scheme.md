[ Клиенты / Курьеры (Web / Mobile) ]
                 |
                 v
[ Amazon CloudFront (CDN) + S3 ] — Хостинг фронтенда (React/Vue)
                 |
                 v
[ Amazon API Gateway ] — Единая точка входа, балансировка, защита от DDoS
   |             |              |
   | (REST)      | (WebSocket)  | (REST)
   v             v              v
[ AWS Lambda ]  [ AWS Lambda ] [ AWS Lambda ] — Микросервисы (Node.js/Python)
(Заказы/ERP)    (Real-time)    (ML-Предсказания)
   |             |              |
   |             |              v
   |             |         [ Amazon SageMaker Serverless ] — ML-модель времени доставки
   v             v
[ Amazon Aurora Serverless v2 ] — Основная БД (PostgreSQL)
(Хранение заказов, пользователей, статусов)
