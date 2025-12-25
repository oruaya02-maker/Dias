# E-commerce Platform Architecture 2025

## 1. Жобаны басқару (Planning)
* **Әдістеме:** Scrum Framework
* **Құралдар:** GitHub Projects & Issues
* **Спринттер:** 1 апталық қарқынды циклдер

## 2. Технологиялық инфрақұрылым
* **Backend:** PHP (Laravel)
* **Frontend:** Next.js (Tailwind CSS)
* **Төлем жүйесі:** Stripe & PayPal API
* **Бұлттық сервис:** Microsoft Azure
* **Контейнерлеу:** Docker

## 3. Сату және төлем жасау схемасы
```mermaid
graph TD
    User((Сатып алушы)) --> Store[Online Store: Next.js]
    Store --> API[Backend API: Laravel]
    API --> Pay{Payment Gateway: Stripe}
    Pay -- Сәтті --o Order[Order System]
    Pay -- Қате --o Store
    Order --> DB[(SQL Server)]
    
    subgraph "Azure Cloud Services"
        App[Azure App Service]
        Data[Azure SQL]
    end
    
    API --- App
    DB --- Data
