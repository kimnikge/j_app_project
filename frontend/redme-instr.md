# 📱 Руководство по адаптации проекта под мобильные устройства

## 🎯 Цель

Создать адаптивный мобильный интерфейс:
- лендингообразные страницы
- фиксированное нижнее меню
- рабочие SVG-иконки
- аккуратная разметка с Tailwind CSS

---

## ✅ Шаг 1: Подключение иконок (Lucide)

Установить:

```bash
npm install lucide-vue-next
```

В `src/main.js` добавить:

```js
import * as lucide from 'lucide-vue-next'

Object.entries(lucide).forEach(([name, component]) => {
  app.component(name, component)
})
```

Теперь доступны иконки как компоненты: `<UserIcon />`, `<HomeIcon />` и т.д.

---

## ✅ Шаг 2: Создание компонента нижнего меню

Создай файл: `src/components/BottomNav.vue`

Содержимое:
- `fixed bottom-0 left-0 right-0 z-50`
- `flex justify-around py-2 bg-white shadow-md`
- Используй `<RouterLink>` и Lucide-иконки

Пример одной кнопки:

```vue
<RouterLink to="/" class="flex flex-col items-center text-xs">
  <HomeIcon class="w-6 h-6" />
  Главная
</RouterLink>
```

---

## ✅ Шаг 3: Подключение `BottomNav` на страницах

1. Внизу каждого компонента страницы добавь:

```vue
<BottomNav />
```

2. Добавь отступ под контент, чтобы меню не перекрывало его:

```html
<div class="pb-[60px]"> ... </div>
```

---

## ✅ Шаг 4: Адаптация страниц под лендинг

В каждой странице:

- Контейнер: `max-w-md mx-auto px-4 pt-4 pb-[60px]`
- Заголовки: `text-xl font-bold`
- Карточки: `rounded-lg shadow p-4 mb-4 bg-white`

Пример:

```vue
<div class="max-w-md mx-auto px-4 pt-4 pb-[60px]">
  <h1 class="text-xl font-bold mb-4">Срочные вакансии</h1>
  <JobCard v-for="job in jobs" :key="job.id" :job="job" />
</div>
```

---

## ✅ Шаг 5: Иконки в карточках

- Заменить устаревшие иконки (пустые квадраты) на Lucide-компоненты:

```vue
<MapPinIcon class="w-5 h-5 text-gray-500 mr-1" />
```

---

## ✅ Шаг 6: Стилизация UI-элементов

### Кнопки:

```html
<button class="bg-gradient-to-r from-orange-500 to-red-500 text-white font-semibold px-4 py-2 rounded">
  Откликнуться
</button>
```

### Бейджи (условия):

```html
<span class="text-green-700 bg-green-100 px-2 py-1 text-xs rounded-full">
  Удалённая работа
</span>
```

---

## ✅ Шаг 7: Проверка

1. Открой сайт в DevTools → Mobile preview
2. Проверь отступ снизу
3. Меню должно быть всегда видно и не перекрывать контент

---

## 🔁 Повторить для всех основных страниц:

- `HomePage.vue`
- `UrgentPage.vue`
- `ResumesPage.vue`
- `JobsPage.vue`
- `ProfilePage.vue`

---

Готово! Проект теперь выглядит и работает как полноценное мобильное приложение 🎉
