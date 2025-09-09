<h1>
  Vue.js <img src="./assets/vuejs.svg" width="40" height="40" />
</h1>

<h2>Найпопулярніші запитання та відповіді на співбесіді з Vue.js</h2>

<details>
<summary>1. Що таке Vue.js і чому його варто використовувати?</summary>

#### Vue.js

**Vue.js** — це прогресивний JavaScript-фреймворк для створення інтерфейсів
користувача. Його використовують через простоту у вивченні, реактивність, легку
інтеграцію у проєкти та сильну екосистему (Vue Router, Pinia, Nuxt). Підходить
як для малих компонентів, так і для масштабних SPA.

</details>

<details>
<summary>2. Як створити новий проєкт на Vue.js?</summary>

#### Vue.js

Для швидкого старту використовують create-vue (офіційний CLI):

```bash
npm create vue@latest
```

Далі обирають потрібні опції (TypeScript, Router, Pinia, ESLint). Або ж можна
інтегрувати Vue у вже існуючий проєкт через npm install vue.

</details>

<details>
<summary>3. Що таке життєвий цикл компонента у Vue.js та які основні хуки існують?</summary>

#### Vue.js

Життєвий цикл — це послідовність етапів, які проходить компонент від створення
до знищення. Основні хуки:

- **onBeforeMount / onMounted** — до та після монтування DOM.

- **onBeforeUpdate / onUpdated** — до та після оновлення реактивних даних.

- **onBeforeUnmount / onUnmounted** — до та після видалення компонента.

- **onActivated / onDeactivated** — для компонентів з `<keep-alive>`.

Вони дозволяють виконувати побічні ефекти (запити, підписки, очищення).

</details>

<details>
<summary>4. Що таке компоненти у Vue.js і як їх використовувати?</summary>

#### Vue.js

Компоненти у Vue.js — це повторно використовувані ізольовані блоки інтерфейсу (з
логікою, шаблоном і стилями).

**Використання:**

1. Оголошуємо компонент (.vue файл або об’єкт).

2. Реєструємо (локально чи глобально).

3. Використовуємо як HTML-тег у шаблоні:

```jsx
<MyButton />
```

</details>

<details>
<summary>5. Як у Vue.js здійснюється прив’язка даних до відображення?</summary>

#### Vue.js

У Vue.js дані зв’язуються реактивно через data binding:

- **Інтерполяція:** `{{ message }}`

- **Атрибути:** `:src="imageUrl"`

- **Двостороння прив’язка:** `v-model="formInput"`

Все це базується на реактивності Vue, тож зміни в стані автоматично оновлюють
DOM.

</details>

<details>
<summary>6. Що таке екземпляр Vue (Vue instance) і для чого він потрібен?</summary>

#### Vue.js

Екземпляр Vue — це об’єкт, створений через `createApp()` (у Vue 3) або
`new Vue()` (у Vue 2). Він є коренем застосунку: керує реактивними даними,
методами, життєвим циклом і рендерингом компонентів у DOM.

</details>

<details>
<summary>7. Що таке віртуальний DOM у Vue.js і як він працює?</summary>

#### Vue.js

Віртуальний DOM — це легка копія реального DOM, яку Vue використовує для
оптимізації оновлень. Коли дані змінюються:

1. Vue оновлює віртуальний DOM.

2. Порівнює його з попередньою версією (diffing).

3. Мінімально оновлює тільки ті частини реального DOM, які змінилися.

Це підвищує продуктивність і зменшує кількість дорогих операцій з DOM.

</details>

<details>
<summary>8. Що таке директиви у Vue.js і які приклади їх використання?</summary>

#### Vue.js

Директиви — це спеціальні атрибути з префіксом v-, які дають Vue інструкції для
роботи з DOM.

Приклади:

- **v-if="isVisible"** — умовне рендерення

- **v-for="item in list"** — рендеринг списків

- **v-model="inputValue"** — двостороння прив’язка

- **v-bind:src="imageUrl"** або скорочено **:src="imageUrl"** — прив’язка
  атрибутів

- **v-on:click="handleClick"** або **@click="handleClick"** — обробка подій

</details>

<details>
<summary>9. Як обробляти введення користувача та відправку форм у Vue.js?</summary>

#### Vue.js

1. Двостороння прив’язка: v-model для input, textarea, select

```jsx
<input v-model="username" />
```

2. Обробка подій: v-on або скорочено @ для submit або click

```jsx
<form @submit.prevent="handleSubmit">
```

3. Методи компонента: у методі handleSubmit обробляємо дані та виконуємо логіку
   (наприклад, валідацію або API-запит).

</details>

<details>
<summary>10. Що таке властивість methods у компоненті Vue і як її використовувати?</summary>

#### Vue.js

`methods` — це об’єкт у компоненті, де визначаються функції для обробки подій
або виконання логіки. Приклад:

```jsx
<script>
export default {
  data() {
    return { count: 0 }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<template>
  <button @click="increment">Натисни</button>
</template>
```

Методи можна викликати в шаблоні або всередині інших методів, вони мають доступ
до this (стану компонента).

</details>

<details>
<summary>11. У чому різниця між v-bind і v-model у Vue.js?</summary>

#### Vue.js

`v-bind` — одностороння прив’язка даних: передає значення зі стану в атрибут
елемента або проп компонента.

```jsx
<img :src="imageUrl" />
```

`v-model` — двостороння прив’язка: синхронізує дані між станом і елементом
форми/компонентом.

```jsx
<input v-model="username" />
```

Тобто v-bind = тільки з даних у DOM, а v-model = в обидві сторони (дані ⇆ DOM).

</details>

<details>
<summary>12. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>13. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>14. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>15. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>16. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>17. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>18. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>19. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>20. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>21. ???</summary>

#### Vue.js

- Coming soon...😎

</details>
