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
<summary>12. Що таке обчислювані властивості (computed properties) у Vue.js і як їх використовувати?</summary>

#### Vue.js

`computed` — це властивості, які обчислюються на основі інших реактивних даних і
кешуються, поки залежності не зміняться.

#### Приклад:

```jsx
<script>
export default {
  data() {
    return { firstName: 'Іван', lastName: 'Петренко' }
  },
  computed: {
    fullName() {
      return this.firstName + ' ' + this.lastName
    }
  }
}
</script>

<template>
  <p>{{ fullName }}</p>
</template>
```

Використовуються для обчислень у шаблоні без дублювання логіки та для
оптимізації (не викликаються щоразу, як methods).

</details>

<details>
<summary>13. У чому різниця між computed та methods у Vue.js?</summary>

#### Vue.js

`computed` — обчислювані властивості, які кешуються і автоматично
перевираховуються лише тоді, коли змінюються їхні залежності. Використовуються
для оптимізованих розрахунків у шаблоні.

`methods` — функції, які виконуються щоразу при виклику, навіть якщо їхні
залежності не змінилися.

- Якщо потрібна оптимізація та реактивність — використовуємо `computed`.
- Якщо потрібна дія чи будь-яка логіка без кешування — `methods`.

</details>

<details>
<summary>14. Що таке спостерігачі (watchers) у Vue.js і для чого вони використовуються?</summary>

#### Vue.js

`watch` — це механізм для відстеження змін у реактивних даних і виконання дій у
відповідь.

#### Приклад:

```jsx
<script>
export default {
  data() {
    return { count: 0 }
  },
  watch: {
    count(newVal, oldVal) {
      console.log(`Зміна: ${oldVal} → ${newVal}`)
    }
  }
}
</script>
```

#### Використовується для:

- реакції на зміну даних (API-запити, збереження у localStorage),

- асинхронних чи "дорогих" операцій, які не доречно виконувати у computed.

</details>

<details>
<summary>15. Як у Vue.js прив’язувати інлайн-стилі в шаблоні?</summary>

#### Vue.js

Інлайн-стилі задаються через v-bind:style (скорочено :style), приймаючи об’єкт
або масив:

```html
<!-- Об’єкт -->
<div :style="{ color: activeColor, fontSize: size + 'px' }"></div>

<!-- Масив об’єктів -->
<div :style="[baseStyle, overrideStyle]"></div>

Також можна прив’язувати динамічні CSS-змінні:

<div :style="{ '--main-color': color }"></div>
```

</details>

<details>
<summary>16. Як у Vue.js передавати дані до дочірнього компонента за допомогою props?</summary>

#### Vue.js

1. У дочірньому компоненті оголошуємо props:

```jsx
<script>
export default {
  props: {
    title: String,
    count: Number
  }
}
</script>
```

2. У батьківському компоненті передаємо значення через атрибути:

```jsx
<ChildComponent :title="pageTitle" :count="items.length" />
```

Props — це односторонній потік даних (від батька до дитини).

</details>

<details>
<summary>17. Що таке default і validator у властивостях props у Vue.js?</summary>

#### Vue.js

У Vue для props можна задати додаткові опції:

- `default` — значення за замовчуванням, якщо проп не переданий:

```js
props: {
  count: {
    type: Number,
    default: 0
  }
}
```

- `validator` — функція для кастомної валідації значення:

```js
props: {
  status: {
    type: String,
    validator: value => ['success', 'error', 'warning'].includes(value)
  }
}
```

Це допомагає робити компонент більш надійним і передбачуваним.

</details>

<details>
<summary>18. Що таке prop drilling у Vue.js і як цього уникати?</summary>

#### Vue.js

**Prop drilling** — це ситуація, коли дані передаються через кілька рівнів
компонентів лише для того, щоб дістатися до "глибокого" дочірнього компонента.
Це ускладнює підтримку коду.

#### Як уникати:

- Використовувати provide/inject для прямої передачі даних вниз по ієрархії.

- Використовувати Pinia або Vuex для глобального стану.

- За потреби — event bus або emit (але тільки для локальних випадків).

У Vue 3 найчастіше застосовують Pinia як стандартне рішення.

</details>

<details>
<summary>19. Що таке слоти у Vue.js і як їх використовувати в компонентах?</summary>

#### Vue.js

Слоти дозволяють передавати вміст від батьківського компонента в дочірній у
визначене місце шаблону.

#### Приклад:

```jsx
<!-- Дочірній компонент -->
<template>
  <div class="card">
    <slot></slot> <!-- місце для вмісту від батька -->
  </div>
</template>

<!-- Батьківський компонент -->
<Card>
  <p>Тут контент для слота</p>
</Card>
```

#### Також є:

- `named slots` — для кількох місць вставки

- `scoped slots` — для передачі даних з дочірнього вмісту батькові

</details>

<details>
<summary>20. Як у Vue.js створити багаторазовий (reusable) компонент?</summary>

#### Vue.js

Щоб зробити компонент багаторазовим:

1. Винести логіку, шаблон і стилі у окремий .vue файл.

2. Використовувати props для налаштувань і слоти для динамічного вмісту.

3. Реєструвати компонент глобально (app.component) або локально у батьківському
   компоненті.

#### Приклад:

```jsx
<!-- Button.vue -->
<template>
  <button :class="typeClass"><slot /></button>
</template>
<script>
export default {
  props: { typeClass: String }
}
</script>

<!-- Використання -->
<MyButton typeClass="primary">Натисни</MyButton>
```

Цей підхід дозволяє повторно використовувати компонент у різних місцях проєкту з
різними даними.

</details>

<details>
<summary>21. Як у Vue.js обробляти нативні події DOM?</summary>

#### Vue.js

Нативні події прив’язуються через директиву v-on або скорочення @:

```html
<button @click="handleClick">Клікни</button>
```

У дочірніх компонентах:

- Якщо елемент емітить власні події (this.$emit), то слухаємо їх звичайно:

```jsx
<ChildComponent @customEvent="doSomething" />
```

- Якщо треба перехопити нативну подію DOM на root-елементі дочірнього компонента
  (у Vue 2) — використовували .native модифікатор:

```jsx
<ChildComponent @click.native="handleClick" />
```

У Vue 3 .native прибрали, натомість треба явно прокидати події (emits) або
вішати обробник напряму на елемент у шаблоні.

</details>

<details>
<summary>22. Що таке поширення подій (event propagation) у Vue.js і як його контролювати?</summary>

#### Vue.js

Поширення подій у Vue.js працює так само, як у звичайному DOM: подія спочатку
йде вниз (capturing), а потім вгору (bubbling) деревом елементів.

#### Як контролювати:

- `.stop` — зупиняє поширення (аналог `event.stopPropagation()`):

```html
<button @click.stop="handleClick">Клік</button>
```

- `.prevent` — скасовує дію браузера (аналог `event.preventDefault()`):

```html
<form @submit.prevent="submitForm"></form>
```

- `.capture` — слухає подію на фазі capturing.

- `.self` — виконує обробник лише якщо подія сталася саме на цьому елементі.

У Vue події можна контролювати чисто через модифікатори, без прямого виклику
`event.stopPropagation()`.

</details>

<details>
<summary>23. Що роблять модифікатори подій .prevent та .stop у Vue.js?</summary>

#### Vue.js

- `.prevent` — викликає `event.preventDefault()`, тобто скасовує стандартну
  поведінку браузера.

```html
<form @submit.prevent="handleSubmit">...</form>
```

- `.stop` — викликає `event.stopPropagation()`, тобто зупиняє подальше поширення
  події вгору по DOM.

```html
<button @click.stop="handleClick">Клік</button>
```

Використовуються для контролю поведінки подій без написання додаткового JS-коду
в методах.

</details>

<details>
<summary>24. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>25. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>26. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>27. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>28. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>29. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>30. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>31. ???</summary>

#### Vue.js

- Coming soon...😎

</details>
