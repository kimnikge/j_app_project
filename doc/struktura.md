# HR-платформа для общепита: Telegram Mini App + Roadmap

## 🍽️ Специализация: Сфера общественного питания

### Целевая аудитория:
- **Основная**: Сотрудники общепита (повара, официанты, бармены, кухонные рабочие, администраторы)
- **Дополнительная**: Смежные специальности (уборщики, курьеры, охранники)

### Особенности сферы:
- ✅ Высокая текучесть кадров - нужна быстрая замена
- ✅ Срочные подмены (больничные, прогулы)
- ✅ Сменная работа и гибкий график
- ✅ Оплата за смену, а не только месячная ЗП
- ✅ Географическая привязка к району работы

---

## 🚀 MVP (Telegram Mini App)

### Цель MVP: Запустить через Telegram за 1-2 недели

### Преимущества Telegram Mini App:
- ✅ Нет необходимости в App Store/Google Play
- ✅ Мгновенная установка через бота
- ✅ Встроенная авторизация через Telegram
- ✅ Бесплатные push-уведомления через бота
- ✅ Доверие пользователей к Telegram
- ✅ Идеально для мобильных сотрудников общепита

---

## 🔧 Техническая архитектура MVP

### Frontend (Telegram Mini App)
```
Технологии:
├── React + Vite (оптимизированный для Telegram WebApp)
├── Telegram WebApp SDK (@twa-dev/sdk)
├── Tailwind CSS (адаптированный для общепита)
├── React Router (SPA навигация)
└── Zustand (легковесный state management)

Дизайн для общепита:
├── Цветовая схема: оранжевый/красный + Telegram цвета
├── Иконки еды и ресторанов
├── Быстрые действия для мобильных работников
├── Адаптация под рабочую среду (быстрый доступ)
└── Крупные элементы управления
```

### Backend (API для Mini App)
```
Технологии:
├── Node.js + Express
├── Supabase (PostgreSQL + Auth + Storage + Real-time)
├── Telegram Bot API (для уведомлений)
├── JWT через Supabase Auth
└── File upload через Supabase Storage

Преимущества Supabase:
├── Готовая авторизация
├── Real-time подписки на новые вакансии
├── Автоматические API endpoints
├── Встроенное хранилище файлов
└── Dashboard для администрирования
```

### Платежная система (не Telegram)
```
Будущая интеграция:
├── Подключение к банковскому API
├── Выставление счетов на тарифы
├── Управление подписками
├── Отчетность по платежам
└── Возможность оплаты картой/СБП
```

---

## 📱 MVP Функциональность (специализированная)

### 🤖 Telegram Bot (точка входа)
```
Команды бота:
├── /start - запуск Mini App
├── /urgent - срочные вакансии/подмены
├── /jobs - обычные вакансии
├── /ready - "готов выйти завтра" (быстрое включение)
├── /profile - профиль и настройки
└── /help - помощь по боту

Уведомления для общепита:
├── 🚨 СРОЧНО: Нужен повар на завтра!
├── 💼 Новые вакансии по вашей специальности
├── 💬 Отклик на вашу вакансию
├── ⚡ Подмена отменилась - освободилось место
└── 📊 Еженедельная сводка по откликам
```

### 👤 Авторизация (через Telegram + Supabase)
```
Интеграция:
├── Telegram авторизация через Supabase
├── Автоматическое получение Telegram данных
├── Выбор роли: соискатель/работодатель
├── Выбор специализации при регистрации
└── Telegram avatar как основное фото

Профиль пользователя:
├── Telegram данные (имя, username, аватар)
├── Роль (job_seeker/employer)  
├── Специализация (повар, официант, бармен, и т.д.)
├── Район работы (предпочтительный)
├── Телефон для быстрой связи
├── Готовность к срочным выходам
└── Статус активности (активен/в поиске/занят)
```

### 📄 Резюме (адаптированное для общепита)
```
Структура резюме:
├── Специальность (повар, официант, бармен и т.д.)
├── Опыт работы (краткое описание, акцент на заведения)
├── Ключевые навыки (теги: "итальянская кухня", "кофе-машина")
├── Зарплатные ожидания (за смену и за месяц)
├── Район работы (несколько районов)
├── График работы (полный день/вечера/выходные)
├── Готовность к подменам (да/нет)
├── Контакты (телефон обязательно)
└── Файл резюме (PDF, до 5МБ) - опционально

Новые поля:
├── ✅ Активность резюме (видимое/скрытое)
├── 🚨 "Готов выйти завтра" (кнопка-переключатель)
├── 📅 До какой даты готов к срочному выходу
└── 💰 Минимальная оплата за смену для срочных вакансий

Интерфейс:
├── Пошаговое создание (4 экрана)
├── Быстрое переключение "готов завтра"
├── Автосохранение через Supabase
├── Предпросмотр в стиле карточки
└── Кнопка "Скрыть/Показать резюме"
```

### 💼 Вакансии (два типа)

#### Обычные вакансии:
```
Структура:
├── Специальность (повар, официант и т.д.)
├── Название заведения
├── Краткое описание (кухня, формат заведения)
├── Зарплата (от-до за месяц)
├── Район/адрес заведения
├── График работы
├── Требования (опыт, навыки)
├── Условия (питание, форма, чаевые)
└── Контакты (Telegram, телефон)

Особенности:
├── Публикация на месяц
├── Статус вакансии (активна/закрыта/на паузе)
├── Счетчик просмотров и откликов
└── Возможность продлить/поднять вакансию
```

#### 🚨 СРОЧНЫЕ вакансии (новый тип):
```
Структура срочной вакансии:
├── "СРОЧНО" - яркий индикатор
├── Специальность + "на подмену"
├── Название заведения
├── Дата выхода (сегодня/завтра/конкретная дата)
├── Смена (утро/день/вечер/ночь с точным временем)
├── 💰 Оплата ЗА СМЕНУ (фиксированная сумма)
├── Район/адрес (обязательно с ближайшим метро)
├── Краткие требования
├── Срочность (через сколько часов нужен ответ)
└── Приоритетные контакты (WhatsApp/Telegram для быстрой связи)

Особенности срочных:
├── Автоматическое закрытие через 24-48 часов
├── Приоритет в показе соискателям с "готов завтра"
├── Push-уведомления всем подходящим кандидатам
├── Возможность "поднять ставку" за смену
└── Быстрые отклики (одна кнопка)
```

### 🔍 Поиск (упрощенный для мобильного)
```
Простые фильтры (кнопки):
├── 🏙️ Район (выпадающий список районов города)
├── 💰 Зарплата (слайдер: за смену/за месяц)
├── 👨‍🍳 Специальность (кнопки: повар, официант, бармен...)
├── 📅 График (полная занятость/подмены/выходные)
└── 🚨 Переключатель "Только срочные"

Быстрый поиск:
├── Строка поиска по ключевым словам
├── Голосовой поиск (через Telegram)
├── Сохраненные фильтры
├── "Очистить все фильтры" одной кнопкой
└── Результаты в режиме реального времени (Supabase)
```

### 📞 Отклики (оптимизированные)
```
Обычный отклик:
├── Кнопка "Откликнуться" → отправка резюме
├── Опциональное сопроводительное сообщение
├── Уведомление работодателю через бота
├── Отслеживание статуса отклика
└── Возможность отозвать отклик

Срочный отклик:
├── 🚨 Кнопка "ГОТОВ ВЫЙТИ" (большая, яркая)
├── Моментальная отправка контактов
├── Автоответ: "Жду звонка в течение часа"
├── Push работодателю + SMS/звонок
└── Статус "ожидаю звонка" с таймером
```

---

## 🗄️ База данных (Supabase)

```sql
-- Пользователи (через Supabase Auth + дополнительные поля)
profiles: 
  id (uuid, FK to auth.users), telegram_id, username, first_name, last_name,
  role, specialization, preferred_districts, phone, email, avatar_url,
  ready_for_urgent, urgent_available_until, created_at, last_active

-- Резюме
resumes: 
  id, user_id, specialization, experience_text, skills, 
  salary_per_shift_min, salary_monthly_min, currency,
  districts, work_schedule, ready_for_substitutions,
  contact_phone, file_url, is_active, ready_tomorrow,
  urgent_min_payment, status, created_at, updated_at

-- Обычные вакансии
jobs: 
  id, employer_id, specialization, establishment_name, description,
  salary_min, salary_max, currency, district, address, metro_station,
  work_schedule, requirements, conditions, contact_telegram, 
  contact_phone, contact_whatsapp, status, expires_at, created_at

-- Срочные вакансии (отдельная таблица)
urgent_jobs:
  id, employer_id, specialization, establishment_name, 
  work_date, shift_start, shift_end, payment_per_shift, currency,
  district, address, metro_station, requirements, 
  response_needed_within_hours, contact_telegram, contact_phone,
  contact_whatsapp, status, auto_close_at, created_at

-- Отклики
applications: 
  id, job_id, urgent_job_id, applicant_id, message, status,
  is_urgent_response, viewed_at, responded_at, created_at

-- Уведомления
notifications:
  id, user_id, type, title, message, data, sent_at, read_at, created_at

-- Специализации (справочник)
specializations:
  id, name, category, is_primary, sort_order

-- Районы (справочник)
districts:
  id, city_id, name, metro_stations, sort_order
```

---

## 📱 Экраны интерфейса

### 🏠 1. Главная страница
```
Контент:
├── 📊 Статистика платформы (живые счетчики)
│   ├── "🔥 143 активных вакансии"
│   ├── "👥 89 человек ищут работу сегодня"
│   └── "⚡ 12 срочных подмен нужны сейчас"
├── 🎠 Карусель рекламы/новостей
│   ├── Реклама ресторанов-партнеров
│   ├── Советы по карьере в общепите
│   └── Истории успеха пользователей
├── 🌟 "Топ вакансии дня" (3-4 лучшие обычные)
├── 🌟 "Лучшие резюме" (3-4 активных кандидата)
└── 🚨 Кнопка "СРОЧНЫЕ ВАКАНСИИ" (если есть)

Дизайн:
├── Яркие карточки с фото блюд/заведений
├── Живые счетчики с анимацией
├── CTA-кнопки в стиле "Откликнуться сейчас"
└── Быстрый доступ к основным разделам
```

### 🚨 2. Экран "СРОЧНО"
```
Интерфейс:
├── 🔥 Заголовок "НУЖНЫ СЕГОДНЯ/ЗАВТРА"
├── ⏰ Таймер до автозакрытия вакансий
├── 📋 Список срочных вакансий (приоритет по времени)
├── 🎯 Кнопка "Я готов выйти завтра" (переключатель)
├── 📱 Уведомления "Новая срочная вакансия!"
└── 💨 Быстрые отклики одной кнопкой

Карточка срочной вакансии:
├── 🚨 "СРОЧНО" бейдж
├── Специальность + заведение
├── 💰 "1500₽ за смену"
├── 📍 Район + метро
├── ⏰ "Нужен завтра в 10:00"
├── 📞 Кнопка "ГОТОВ!" (большая, зеленая)
└── ⏳ "Ответ нужен в течение 2 часов"
```

### 💼 3. Экран "Вакансии"
```
Фильтры (горизонтальная прокрутка):
├── [🏙️ Все районы ▼] [💰 Любая ЗП ▼] [👨‍🍳 Все ▼] [📅 График ▼]
├── Кнопка "Очистить фильтры"
└── Переключатель "Только с жильем" / "Только с опытом"

Список вакансий:
├── Сортировка: новые/по зарплате/по рейтингу
├── Карточки с превью фото заведения
├── Быстрые действия: ❤️ 📑 📤 (отклик/сохранить/поделиться)
├── Infinite scroll
└── Pull-to-refresh для обновления

Карточка вакансии:
├── 📸 Фото заведения (или дефолтное по типу кухни)
├── Специальность + название заведения
├── 💰 "25,000-35,000₽/мес"
├── 📍 Район, ближайшее метро
├── ⏰ График работы
├── 👥 "5 откликов" (показать конкуренцию)
└── Кнопки действий
```

### 👥 4. Экран "Резюме"
```
Фильтры для работодателей:
├── [👨‍🍳 Специальность ▼] [🏙️ Район ▼] [💰 ЗП ожидания ▼]
├── ✅ "Только готовые к срочным выходам"
├── ✅ "Только с опытом работы"
└── Сортировка: новые/по активности/по рейтингу

Карточка резюме:
├── 👤 Фото (аватар Telegram или загруженное)
├── Имя + специальность + опыт
├── 💰 "от 1200₽/смена"  
├── 📍 Готов работать в: [районы]
├── 🚨 Бейдж "Готов завтра!" (если включено)
├── ⭐ Рейтинг/отзывы (в будущих обновлениях)
├── 📱 Кнопка "Связаться"
└── 👁️ "Просмотрено 15 раз на этой неделе"

Быстрые действия для соискателей:
├── 🔄 "Поднять резюме" (обновить дату)
├── 👁️ "Скрыть/показать резюме"
├── 🚨 "Готов завтра" (переключатель)
└── ✏️ "Редактировать"
```

### 👤 5. Экран "Профиль"
```
Для соискателя:
├── 📊 Статистика резюме (просмотры, отклики)
├── 📄 "Мое резюме" → редактирование
├── 📥 "Мои отклики" (история со статусами)
├── 🚨 "Готовность к срочным выходам" (настройки)
├── ⚙️ Настройки уведомлений
├── 📱 Контактные данные
└── 🏆 Достижения/рейтинг (будущие фичи)

Для работодателя:
├── 📊 Статистика вакансий (просмотры, отклики)
├── ➕ "Создать обычную вакансию"
├── 🚨 "Создать срочную вакансию"
├── 📋 "Мои вакансии" (управление)
├── 👥 "Отклики на мои вакансии"
├── 💰 Тарифы и подписки (будущие фичи)
├── ⚙️ Настройки аккаунта
└── 📈 Аналитика (продвинутые метрики)

Универсальные элементы:
├── 🌙 Переключатель темы
├── 🔔 Настройки уведомлений  
├── ❓ Помощь и FAQ
├── 📞 Поддержка
└── 🚪 Выход
```

---

## 🎨 Критерии дизайна и оформления

### Цветовая схема "Общепит":
```
Основные цвета:
├── Основной: #FF6B35 (теплый оранжевый - ассоциация с едой)
├── Акцент: #F7931E (золотисто-оранжевый)
├── Успех: #4CAF50 (зеленый для "готов", "доступен")
├── Срочно: #FF3D00 (ярко-красный для срочных вакансий)
├── Предупреждение: #FFC107 (желтый)
└── Нейтральный: #757575 (серый для текста)

Telegram интеграция:
├── Использование переменных темы Telegram
├── Поддержка светлая/темная тема
├── Цвета кнопок адаптированы под Telegram
└── Haptic feedback на все основные действия
```

### Типографика для мобильных:
```
Иерархия шрифтов:
├── H1: 24px, жирный (заголовки страниц)
├── H2: 20px, полужирный (заголовки секций)  
├── H3: 18px, полужирный (заголовки карточек)
├── Body: 16px, обычный (основной текст)
├── Caption: 14px, обычный (подписи, мета-инфо)
└── Small: 12px, обычный (timestamps, счетчики)

Особенности:
├── Увеличенный line-height для читаемости на мобильном
├── Контрастные цвета для текста
├── Жирное выделение важной информации (зарплата, сроки)
└── Emoji в заголовках для быстрого распознавания
```

### UI-компоненты:
```
Кнопки:
├── Основные: height 48px (thumb-friendly)
├── Вторичные: height 40px  
├── Малые: height 32px
├── Скругление: 8px (современный вид)
├── Тени: subtle shadow для глубины
└── Hover/active состояния с анимацией

Карточки:
├── Padding: 16px
├── Скругление: 12px
├── Тень: box-shadow для выделения
├── Hover эффект: легкое увеличение (transform: scale(1.02))
└── Загрузка: skeleton loading для лучшего UX

Формы:
├── Input height: 48px
├── Скругление: 8px
├── Focus состояние: подсветка accent цветом
├── Ошибки: красная подсветка + иконка
└── Placeholders: нейтральный цвет с примерами
```

### Адаптивность и анимации:
```
Мобильная оптимизация:
├── Минимальная область нажатия: 44x44px
├── Отступы между элементами: минимум 8px
├── Горизонтальные отступы: 16px от краев экрана
├── Sticky элементы: поиск, фильтры
└── Safe area учет для iOS

Микроанимации:
├── Переходы: 200ms ease-out
├── Загрузка: skeleton + fade-in
├── Успешные действия: checkmark анимация
├── Haptic feedback: на все CTA кнопки
└── Pull-to-refresh: стандартная анимация

Состояния загрузки:
├── Skeleton для карточек
├── Spinner для кнопок действий
├── Прогресс бар для загрузки файлов
└── Пустые состояния с полезными подсказками
```

---

## 🔧 Улучшения и недостающие элементы

### 📊 Системы рейтингов и отзывов:
```
Для работодателей:
├── Рейтинг заведения (1-5 звезд)
├── Отзывы от сотрудников
├── Показатели: "вовремя платят", "хорошие условия"
├── Blacklist проблемных работодателей
└── Верификация заведений (синяя галочка)

Для соискателей:
├── Рейтинг надежности (приходит на работу)
├── Отзывы от работодателей
├── Профессиональные навыки (подтвержденные)
├── История работы (где и сколько проработал)
└── Бейджи достижений ("Пунктуальный", "Опытный")
```

### 🔔 Умные уведомления:
```
Персонализированные:
├── Время отправки на основе активности пользователя
├── Частота на основе предпочтений
├── Контент на основе специализации и района
├── "Не беспокоить" в рабочее время для работающих
└── Срочные уведомления даже в режиме "не беспокоить"

Типы уведомлений:
├── 🚨 Push для срочных вакансий (высокий приоритет)
├── 📱 Обычные push для новых вакансий
├── 📧 Weekly digest по email (опционально)
├── 💬 Сообщения в Telegram боте
└── 📲 SMS для критически важных (платно)
```

### 📈 Простая аналитика:
```
Для соискателей:
├── "Ваше резюме просмотрели 23 раза за неделю"
├── "5 работодателей сохранили ваше резюме"
├── "Средняя зарплата поваров в вашем районе: 28,000₽"
├── "Лучшее время для поиска работы: вторник утром"
└── Советы по улучшению резюме

Для работодателей:
├── "Вашу вакансию просмотрели 156 человек"
├── "12 подходящих кандидатов в вашем районе"
├── "Средняя зарплата для этой позиции: 35,000₽"
├── "Время отклика кандидатов: 4 часа"
└── Рекомендации по улучшению вакансии
```

### 🤝 Социальные функции:
```
Сообщество:
├── Чат для обмена опытом между коллегами
├── Советы и лайфхаки от опытных работников
├── Группы по специализациям
├── Обсуждение работодателей (анонимно)
└── Менторство (опытные помогают новичкам)

Геймификация:
├── Достижения за активность
├── Уровни профиля (новичок → профи → эксперт)
├── Еженедельные челленджи
├── Топ активных пользователей
└── Бонусы за качественные отзывы
```

### 💰 Монетизация (подготовка):
```
Базовый план (бесплатно):
├── 1 активное резюме
├── 3 отклика в день
├── Просмотр вакансий
├── Базовые уведомления
└── Доступ к обычным вакансиям

Премиум план (для соискателей):
├── Неограниченные резюме и отклики
├── Приоритет в показе резюме
├── Расширенная аналитика
├── Первые на срочные вакансии
├── Персональные рекомендации
└── Без рекламы

Бизнес план (для работодателей):
├── Неограниченные вакансии
├── Выделение вакансий цветом
├── Доступ к резюме с контактами
├── Расширенная аналитика откликов
├── Массовая рассылка подходящим кандидатам
└── Приоритетная поддержка
```

### 🔒 Безопасность и модерация:
```
Защита пользователей:
├── Верификация работодателей по ИНН
├── Проверка вакансий на мошенничество
├── Жалобы и блокировки
├── Скрытие контактов до взаимного интереса
└── Автомодерация текстов на неприемлемый контент

Качество контента:
├── AI-проверка вакансий на адекватность
├── Модерация фото профилей
├── Проверка на дубли вакансий/резюме
├── Фильтр спама в откликах
└── Система репутации пользователей
```

---

## 🚀 План развития (обновленный)

### MVP (1-2 недели):
- ✅ Telegram Mini App с базовым функционалом
- ✅ Обычные и срочные вакансии/резюме
- ✅ Простой поиск и отклики
- ✅ Supabase интеграция
- ✅ Telegram Bot для уведомлений

### Update 1 (3-4 недели):
- ✅ Система рейтингов и отзывов
- ✅ Умные уведомления
- ✅ Улучшенный поиск с сохранением фильтров
- ✅ Базовая аналитика для пользователей

### Update 2 (5-8 недель):
- ✅ Платежная система через банк
- ✅ Тарифные планы и подписки
- ✅ Продвинутая аналитика и инсайты
- ✅ Система верификации работодателей
- ✅ Расширенная модерация контента

### Update 3 (9-12 недель):
- ✅ AI-рекомендации вакансий и кандидатов
- ✅ Социальные функции (чаты, сообщества)
- ✅ Геймификация и достижения
- ✅ Интеграция с внешними HR-системами
- ✅ Мобильное приложение (если потребуется)

---

## 📋 Чек-лист для MVP запуска

### Техническая подготовка:
- [ ] Настроить Supabase проект (база, авторизация, storage)
- [ ] Создать Telegram Bot и получить токен
- [ ] Настроить Telegram Mini App в BotFather
- [ ] Развернуть фронтенд с базовым функционалом
- [ ] Настроить webhook для Telegram Bot
- [ ] Подключить домен и SSL сертификат
- [ ] Настроить мониторинг и логирование

### Контент и данные:
- [ ] Создать справочник специализаций общепита
- [ ] Добавить справочник районов города
- [ ] Подготовить иконки и изображения для UI
- [ ] Создать шаблоны уведомлений
- [ ] Написать тексты для помощи и FAQ
- [ ] Подготовить примеры вакансий и резюме для демо

### Тестирование:
- [ ] Протестировать все сценарии пользователей
- [ ] Проверить работу на разных устройствах
- [ ] Тест интеграции с Telegram
- [ ] Нагрузочное тестирование базовых функций
- [ ] Проверка безопасности и валидации данных

### Запуск:
- [ ] Создать промо-материалы для Telegram каналов
- [ ] Подготовить инструкции для первых пользователей
- [ ] Настроить аналитику (Google Analytics, Яндекс.Метрика)
- [ ] Создать техподдержку через Telegram
- [ ] Запланировать стратегию привлечения первых пользователей

---

## 🎯 Ключевые особенности платформы

### Преимущества для сферы общепита:
1. **Скорость**: Мгновенные уведомления о срочных подменах
2. **Мобильность**: Полностью адаптировано для работы на смартфоне
3. **Специализация**: Заточено под потребности ресторанного бизнеса
4. **Доступность**: Работает через популярный Telegram
5. **Простота**: Минимум действий для поиска работы или сотрудников

### Уникальные функции:
- 🚨 **Срочные вакансии** с оплатой за смену
- ⚡ **"Готов завтра"** - мгновенная готовность к работе
- 📍 **Районный поиск** - работа рядом с домом
- 💰 **Прозрачные зарплаты** - реальные цифры без скрытых условий
- 🔔 **Умные уведомления** - только релевантные предложения

### Социальная значимость:
- Помогает решить проблему высокой текучести в общепите
- Снижает время поиска работы для сотрудников
- Уменьшает простои заведений из-за нехватки персонала
- Создает прозрачный рынок труда в сфере общепита
- Повышает стандарты условий труда через систему отзывов

---

## 🚀 Заключение

Данная HR-платформа для общепита через Telegram Mini App представляет собой инновационное решение, которое:

### Решает реальные проблемы:
- **Для соискателей**: быстрый поиск работы, срочные подмены, прозрачные условия
- **Для работодателей**: мгновенный поиск замены, качественные кандидаты, экономия времени
- **Для отрасли**: снижение текучести, повышение стандартов, развитие профессионального сообщества

### Использует современные технологии:
- **Telegram Mini App** - для максимальной доступности
- **Supabase** - для быстрой разработки и масштабирования  
- **Real-time уведомления** - для мгновенной реакции на запросы
- **AI-powered рекомендации** - для точного подбора вакансий и кандидатов

### Обеспечивает быстрый запуск:
- MVP можно запустить за **1-2 недели**
- Минимальные затраты на разработку
- Нет необходимости в модерации App Store/Google Play
- Встроенная аудитория Telegram пользователей

Эта платформа имеет потенциал стать главным инструментом для поиска работы и сотрудников в сфере общественного питания, благодаря своей специализации, удобству использования и инновационным подходам к решению отраслевых проблем.