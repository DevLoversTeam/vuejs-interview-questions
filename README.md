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
<summary>24. Коли у Vue.js варто використовувати модифікатор події .once?</summary>

#### Vue.js

- `.once` змушує обробник події виконатися лише один раз для цього елемента,
  після чого він автоматично знімається.

#### Приклад:

```html
<button @click.once="handleClick">Клікни один раз</button>
```

Використовується, коли потрібно одноразове виконання дії (наприклад, реєстрація
користувача, початковий запит до API, показ повідомлення).

</details>

<details>
<summary>25. У Vue події створюються через $emit у дочірньому компоненті та слухаються у батьківському.</summary>

#### Vue.js

- Приклад:

```html
<!-- Child.vue -->
<template>
  <button @click="$emit('increment', 1)">+1</button>
</template>

<!-- Parent.vue -->
<template>
  <Child @increment="handleIncrement" />
</template>

<script>
  export default {
    methods: {
      handleIncrement(value) {
        console.log('Отримав від дитини:', value);
      },
    },
  };
</script>
```

- У Vue 3 бажано явно описувати події в опції emits:

```js
emits: ['increment'];
```

- Це робить код більш передбачуваним і зрозумілим.

</details>

<details>
<summary>26. Для чого використовуються директиви v-if та v-for у Vue.js?</summary>

#### Vue.js

`v-if` — умовне рендерення: додає або видаляє елемент з DOM залежно від умови.

```html
<p v-if="isLoggedIn">Привіт, користувачу!</p>
```

`v-for` — ітерація: рендерить список елементів на основі масиву чи об’єкта.

```html
<li v-for="item in items" :key="item.id">{{ item.name }}</li>
```

Разом їх треба використовувати обережно (v-if має пріоритет над v-for).

</details>

<details>
<summary>27. Як використовується директива v-show у Vue.js і чим вона відрізняється від v-if?</summary>

#### Vue.js

- `v-show` — приховує/показує елемент через CSS (display: none), але елемент
  завжди присутній у DOM.

```html
<p v-show="isVisible">Привіт!</p>
```

- `v-if` — додає або повністю видаляє елемент із DOM залежно від умови.

```html
<p v-if="isVisible">Привіт!</p>
```

Використовуємо v-if, коли елемент може взагалі не існувати, а v-show — коли
треба часто перемикати видимість без перевідтворення DOM.

</details>

<details>
<summary>28. Які вбудовані директиви є у Vue.js та для чого вони використовуються?</summary>

#### Vue.js

Основні вбудовані директиви Vue.js:

- `v-bind` — прив’язка атрибутів/props до даних.

- `v-model` — двостороння прив’язка між станом і формою.

- `v-if` / `v-else-if` / `v-else` — умовне рендерення.

- `v-show` — показ/приховування елемента через CSS.

- `v-for` — рендеринг списків.

- `v-on` — обробка подій.

- `v-slot` — робота зі слотами.

- `v-pre` — пропускає компіляцію шаблону (показує як є).

- `v-once` — рендерить елемент один раз (не оновлюється при змінах).

- `v-html` — вставка сирого HTML (застосовувати обережно).

Ці директиви дають змогу легко керувати DOM без прямого маніпулювання ним.

</details>

<details>
<summary>29. У чому основні відмінності між v-bind та v-on у Vue.js?</summary>

#### Vue.js

- `v-bind` — використовується для прив’язки даних до атрибутів або props.

```html
<img :src="imageUrl" /> <ChildComponent :title="pageTitle" />
```

- `v-on` — використовується для прив’язки обробників подій до елементів чи
  компонентів.

```html
<button @click="handleClick">Клік</button>
<ChildComponent @customEvent="doSomething" />
```

Коротко: v-bind = дані → атрибут, v-on = подія → метод.

</details>

<details>
<summary>30. Як у Vue.js використовувати render-функцію?</summary>

#### Vue.js

Render-функція дозволяє будувати віртуальний DOM напряму за допомогою
JavaScript, без шаблонів. Використовується для динамічного або умовного
створення складних структур.

#### Приклад (Vue 3):

```js
import { h } from 'vue';

export default {
  render() {
    return h('button', { onClick: () => alert('Клік!') }, 'Натисни');
  },
};
```

#### Використовують, коли:

- потрібен повний контроль над створенням елементів,

- пишуть високорівневі UI-бібліотеки (наприклад, Vuetify, Element Plus),

- треба умовно чи програмно будувати структуру.

</details>

<details>
<summary>31. Що таке Vuex і для чого він використовується?</summary>

#### Vue.js

Vuex — це офіційна бібліотека для глобального управління станом у Vue 2/3. Вона
базується на концепції єдиного сховища (store) з чіткими правилами зміни даних.

**Основні частини:**

- `state` — глобальні дані

- `getters` — обчислені властивості над state

- `mutations` — синхронні зміни state

- `actions` — асинхронна логіка, що викликає mutations

- `modules` — поділ стану на частини

У Vue 3 новим стандартом стала Pinia, але Vuex ще часто зустрічається у великих
проєктах.

</details>

<details>
<summary>32. Що таке store у Vuex і яку роль він виконує?</summary>

#### Vue.js

**Store** — це центральне сховище даних у Vuex, яке містить увесь глобальний
стан застосунку.

#### Його роль:

- забезпечує єдине джерело правди для всіх компонентів;

- дозволяє компонентам зчитувати дані через state і getters;

- змінювати дані тільки через контрольовані механізми — mutations (синхронно) та
  actions (асинхронно).

#### Приклад створення store:

```JavaScript
import { createStore } from 'vuex'

const store = createStore({
  state: { count: 0 },
  mutations: {
    increment(state) { state.count++ }
  }
})
```

Store робить стан передбачуваним і спрощує відлагодження у великих Vue-додатках.

</details>

<details>
<summary>33. Як можна керувати станом у Vue.js без використання Vuex?</summary>

#### Vue.js

Без Vuex є кілька способів:

1. **Props + events (emits)** – передача даних згори вниз (props) і підйом подій
   знизу вгору (emits). Підходить для невеликих додатків.

2. **Provide / Inject** – передача стану через ієрархію компонентів без
   проп-дріллінгу.

3. **Composition API (reactive, ref)** – створення власних composables для
   збереження та повторного використання стану.

4. **Pinia** – офіційно рекомендований lightweight store для Vue 3 (альтернатива
   Vuex).

5. **LocalStorage / sessionStorage** – для збереження стану між
   перезавантаженнями сторінки.

Найчастіше у Vue 3 без Vuex застосовують Pinia або Composition API.

</details>

<details>
<summary>34. Які основні концепції (core concepts) у Vuex?</summary>

#### Vue.js

Vuex базується на таких ключових концепціях:

1. **State** – єдине джерело глобального стану додатку.

2. **Getters** – обчислені властивості для state (аналог computed).

3. **Mutations** – синхронні методи для зміни state.

4. **Actions** – асинхронна логіка, яка може викликати mutations.

5. **Modules** – розбиття store на незалежні підмодулі для масштабування.

Це забезпечує передбачуваний, централізований і структурований спосіб керування
даними.

</details>

<details>
<summary>35. Яке призначення mutations та actions у Vuex?</summary>

#### Vue.js

- **Mutations** – єдиний спосіб синхронно змінювати state. Вони завжди прості,
  передбачувані та відстежувані.

- **Actions** – містять асинхронну логіку (наприклад, API-запити) і в кінці
  викликають mutations для зміни стану.

#### Коротко:

- Mutations = зміна стану

- Actions = бізнес-логіка + асинхронність

</details>

<details>
<summary>36. Що таке Vue Router і для чого він використовується?</summary>

#### Vue.js

Vue Router — це офіційна бібліотека маршрутизації для Vue.js. Вона
використовується для:

- створення SPA (Single Page Application) з багатьма сторінками без повного
  перезавантаження;

- визначення шляхів (routes) та відображення відповідних компонентів;

- роботи з динамічними маршрутами, параметрами, guard'ами, lazy loading.

Коротко: Vue Router дозволяє організувати навігацію у Vue-застосунках.

</details>

<details>
<summary>37. Як налаштувати маршрутизацію (routing) у Vue.js-застосунку?</summary>

#### Vue.js

1. Встановити Vue Router

```bash
npm install vue-router
```

2. Створити файл маршрутизації (router/index.js):

```JavaScript
import { createRouter, createWebHistory } from 'vue-router'
import Home from '../views/Home.vue'
import About from '../views/About.vue'

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About }
]

const router = createRouter({
  history: createWebHistory(),
  routes
})

export default router
```

3. Підключити router у main.js:

```JavaScript
import { createApp } from 'vue'
import App from './App.vue'
import router from './router'

createApp(App).use(router).mount('#app')
```

4. Використати router-link та router-view:

```html
<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>
```

Це базове налаштування. Для реальних проєктів додають динамічні маршрути, lazy
loading, guard’и.

</details>

<details>
<summary>38. Як у Vue.js здійснюється навігація між сторінками?</summary>

#### Vue.js

Є два основних способи:

1. Декларативний — через компонент `<router-link>`:

```html
<router-link to="/about">About</router-link>
```

2. Програмний — через об’єкт router:

```JavaScript
this.$router.push('/about')      // Vue 2
router.push('/about')            // Vue 3 (Composition API)
```

У Vue 3 з Composition API використовують useRouter():

```JavaScript
import { useRouter } from 'vue-router'

const router = useRouter()
router.push({ name: 'about' })
```

</details>

<details>
<summary>39. Що таке динамічний маршрут у Vue Router і як його створити?</summary>

#### Vue.js

Динамічний маршрут — це маршрут із параметрами, які змінюються залежно від URL
(наприклад, user/1, user/2).

#### Створення:

У файлі router/index.js:

```JavaScript
import { createRouter, createWebHistory } from 'vue-router'
import User from '../views/User.vue'

const routes = [
  { path: '/user/:id', component: User }
]

const router = createRouter({
  history: createWebHistory(),
  routes
})

export default router
```

#### Доступ до параметра в компоненті:

Options API:

```JavaScript
this.$route.params.id
```

Composition API:

```JavaScript
import { useRoute } from 'vue-router'
const route = useRoute()
console.log(route.params.id)
```

Використовується для сторінок профілю, деталей товарів, постів тощо.

</details>

<details>
<summary>40. Як у Vue Router реалізуються вкладені (nested) маршрути?</summary>

#### Vue.js

Вкладені маршрути дозволяють відображати дочірні компоненти всередині
батьківського через <router-view>.

#### Приклад конфігурації:

```js
import { createRouter, createWebHistory } from 'vue-router';
import User from '../views/User.vue';
import UserProfile from '../views/UserProfile.vue';
import UserPosts from '../views/UserPosts.vue';

const routes = [
  {
    path: '/user/:id',
    component: User,
    children: [
      { path: 'profile', component: UserProfile },
      { path: 'posts', component: UserPosts },
    ],
  },
];

const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default router;
```

#### У компоненті User.vue:

```html
<template>
  <div>
    <h2>User {{ $route.params.id }}</h2>
    <router-link :to="`/user/${$route.params.id}/profile`">Profile</router-link>
    <router-link :to="`/user/${$route.params.id}/posts`">Posts</router-link>

    <!-- Тут рендеряться дочірні -->
    <router-view />
  </div>
</template>
```

Це зручно для побудови ієрархій сторінок: профіль користувача → налаштування →
пости.

</details>

<details>
<summary>41. Що таке mixins у Vue.js і як їх використовують?</summary>

#### Vue.js

**Mixins** — це механізм повторного використання логіки між різними
компонентами. Вони дозволяють винести загальні дані, методи, lifecycle hooks у
окремий об’єкт і підключати його в компоненти.

Приклад створення та використання:

```JavaScript
// mixins/logger.js
export default {
  data() {
    return { logCount: 0 }
  },
  methods: {
    logMessage(msg) {
      this.logCount++
      console.log(`[${this.logCount}] ${msg}`)
    }
  }
}

```

```html
<script>
  import logger from '../mixins/logger';

  export default {
    mixins: [logger],
    mounted() {
      this.logMessage('Компонент змонтовано');
    },
  };
</script>
```

Недолік — можливі конфлікти імен і важче відслідковувати звідки береться логіка.

У Vue 3 частіше замінюють на Composition API (composables).

</details>

<details>
<summary>42. Як у Vue.js відбувається злиття (merge) опцій компонента з mixins?</summary>

#### Vue.js

При підключенні mixin Vue об’єднує його опції з опціями компонента за певними
правилами:

- **data** → об’єднується, але у випадку конфлікту ключів пріоритет має
  компонент.

- **methods, components, directives** → об’єднуються, а при конфлікті перемагає
  компонент.

- **lifecycle hooks** → виконуються усі (спочатку з mixin, потім із компонента).

- **watchers** → теж об’єднуються, викликаються всі відповідні.

#### Приклад:

```JavaScript
const mixin = {
  data() {
    return { message: 'з mixin' }
  },
  created() {
    console.log('Mixin created')
  }
}

export default {
  mixins: [mixin],
  data() {
    return { message: 'з компонента' }
  },
  created() {
    console.log('Component created')
  }
}
```

Результат: message = 'з компонента', у консолі:

```
Mixin created
Component created
```

</details>

<details>
<summary>43. Що таке кастомна (custom) директива у Vue.js і як її створити?</summary>

#### Vue.js

Кастомна директива дозволяє розширювати HTML новою поведінкою, яку можна
повторно використовувати в компонентах.

#### Приклад створення глобальної директиви (Vue 3):

```JavaScript
// main.js
import { createApp } from 'vue'
import App from './App.vue'

const app = createApp(App)

app.directive('focus', {
  mounted(el) {
    el.focus()
  }
})

app.mount('#app')
```

#### Використання у компоненті:

```html
<template>
  <input v-focus />
</template>
```

- Це спрацює як вбудована директива autofocus, але з власною логікою.

- Кастомні директиви часто застосовують для роботи з DOM напряму (фокус, scroll,
  валідація, анімації).

</details>

<details>
<summary>44. Як зареєструвати глобальну директиву у Vue.js?</summary>

#### Vue.js

У Vue 3 глобальні директиви реєструють через app.directive(). Вони стають
доступними в усіх компонентах додатку.

#### Приклад:

```JavaScript
// main.js
import { createApp } from 'vue'
import App from './App.vue'

const app = createApp(App)

// реєстрація глобальної директиви v-focus
app.directive('focus', {
  mounted(el) {
    el.focus()
  }
})

app.mount('#app')
```

#### Використання у будь-якому компоненті:

```html
<template>
  <input v-focus />
</template>
```

- У Vue 2 це робилось через Vue.directive('focus', { ... }).

</details>

<details>
<summary>45. Який є практичний приклад використання кастомних директив у Vue.js?</summary>

#### Vue.js

Практичний кейс — автоматичний фокус на інпут при завантаженні форми. Це зручно
для логін- або пошукових форм.

#### Приклад кастомної директиви v-focus:

```JavaScript
app.directive('focus', {
  mounted(el) {
    el.focus()
  }
})
```

```html
<template>
  <input v-focus placeholder="Введіть логін" />
</template>
```

#### Інші реальні приклади:

`v-scroll` — відстеження скролу сторінки (наприклад, показ кнопки "наверх").

`v-click-outside` — закриття модальних вікон/меню при кліку поза ними.

`v-lazy-load` — відкладене завантаження зображень.

Використовують тоді, коли потрібен прямий контроль над DOM, який важко
реалізувати через стандартні засоби Vue.

</details>

<details>
<summary>46. Що таке Vue CLI і які його можливості?</summary>

#### Vue.js

Vue CLI — це офіційний інструмент командного рядка для швидкого створення та
налаштування Vue-проєктів.

#### Основні можливості:

- Генерація нового проєкту з готовою структурою.

- Вбудовані конфігурації Webpack (не треба налаштовувати вручну).

- Підтримка плагінів (Vue Router, Vuex, TypeScript, ESLint тощо).

- Hot Module Replacement (HMR) — миттєве оновлення при зміні коду.

- Команди для build, serve, test, lint.

- Можливість кастомізувати конфіг через vue.config.js.

У Vue 3 новим стандартом став Vite, бо він швидший і простіший. Але Vue CLI ще
активно використовується у багатьох проєктах.

</details>

<details>
<summary>47. Як додати препроцесор (наприклад, SASS/SCSS) у Vue-проєкт?</summary>

#### Vue.js

У Vue (CLI чи Vite) SASS/SCSS підключається через встановлення потрібних
залежностей.

1. Встановити пакети:

```bash
npm install -D sass
```

(у Vue CLI раніше треба було sass-loader, у Vite достатньо sass).

2. Використати в компоненті:

```html
<template>
  <div class="box">Hello</div>
</template>

<style lang="scss">
  .box {
    padding: 20px;
    background: lighten(#42b983, 20%);
  }
</style>
```

3. Глобальні стилі (опціонально):

- У Vue CLI — вказати в vue.config.js → css.loaderOptions.sass.

- У Vite — імпортувати у main.js або через vite.config.js →
  css.preprocessorOptions.

Після цього можна писати стилі у .vue з lang="scss" або створювати окремі .scss
файли.

</details>

<details>
<summary>48. Яке призначення Vue DevTools?</summary>

#### Vue.js

Vue DevTools — це офіційне розширення для браузера (Chrome/Firefox), яке спрощує
відлагодження Vue-застосунків.

**Основні можливості:**

- Інспектування структури компонентів та їхніх props, data, computed.

- Перегляд і зміна стану Vuex/Pinia у реальному часі.

- Відстеження подій (events) між компонентами.

- Таймлайн (performance) для аналізу рендерингу.

- Можливість «time-travel debugging» — переглядати попередні стани.

Це головний інструмент для дебагу Vue-проєктів, подібний до React DevTools у
світі React.

</details>

<details>
<summary>49. Як налаштувати Vue.js-проєкт для роботи з різними оточеннями (development, staging, production)?</summary>

#### Vue.js

У Vue.js це робиться через файли середовища (.env).

1. Створити файли:

```bash
.env              # спільні змінні
.env.development  # тільки для dev
.env.production   # тільки для prod
.env.staging      # для staging
```

2. Додати змінні:

```bash
VITE_API_URL=https://api.dev.example.com
```

⚠️ У Vite всі змінні повинні починатися з `VITE_`.

3. Використати у коді:

```JavaScript
console.log(import.meta.env.VITE_API_URL)
```

4. Налаштування запуску:

- `npm run dev` → використовує `.env.development`

- `npm run build` → використовує `.env.production`

- можна створювати кастомні скрипти для staging.

Це дозволяє мати різні API endpoints, ключі чи конфігурації під різні
середовища.

</details>

<details>
<summary>50. Як можна оптимізувати продуктивність Vue.js-застосунку?</summary>

#### Vue.js

**Основні техніки оптимізації:**

1. Ліниве завантаження (lazy loading) компонентів і маршрутів через import().

2. Memoization через computed — мінімізувати зайві перерахунки.

3. Virtual DOM оптимізації:

- використовувати key у списках,

- v-once для статичних елементів,

- v-memo у Vue 3.2+.

4. Компонентний рівень: ділити великі компоненти на дрібні.

5. Оптимізація списків — virtual scroll для великих наборів даних.

6. Debounce/throttle для input та scroll-подій.

7. Кешування даних (Vuex/Pinia, composables, IndexedDB/LocalStorage).

8. Оптимізація зображень та асетів (webp, responsive images, CDN).

9. Production build — мінімізація, tree-shaking, вимкнення devtools.

10. Suspense + async components для плавного UX.

Vue вже добре оптимізований «з коробки», але ці кроки потрібні для великих SPA.

</details>

<details>
<summary>51. Що таке функціональні компоненти у Vue.js?</summary>

#### Vue.js

Функціональні компоненти — це легковагові компоненти без стану (data) та
життєвого циклу, які рендеряться швидше, бо вони просто функція, яка повертає
VNode. Використовуються для простих, презентаційних компонентів.

- **Приклад (Vue 3, Composition API):**

```JavaScript
// FunctionalComponent.vue
export default {
  functional: true,
  props: {
    text: String
  },
  render(h, ctx) {
    return h('p', ctx.props.text)
  }
}
```

- **У Vue 3 часто просто пишуть як функцію:**

```JavaScript
const FunctionalComponent = (props) => h('p', props.text)
```

</details>

<details>
<summary>52. Як використовувати provide та inject у Vue.js?</summary>

#### Vue.js

`provide` і `inject` дозволяють передавати дані від батьківського компонента до
будь-якого нащадка на будь-якому рівні ієрархії без пропсів.

#### Приклад (Vue 3, Composition API):

```JavaScript
// Parent.vue
import { provide, ref } from 'vue'

export default {
  setup() {
    const user = ref('Andriy')
    provide('user', user)
  }
}

// Child.vue
import { inject } from 'vue'

export default {
  setup() {
    const user = inject('user')
    return { user }
  },
  template: `<p>User: {{ user }}</p>`
}
```

#### Особливості:

- `provide` визначає ключ і значення для передачі.

- `inject` отримує значення за ключем.

- Дані реактивні, якщо передавати ref або reactive.

</details>

<details>
<summary>53. Як відбувається реєстрація компонентів у Vue.js?</summary>

#### Vue.js

У Vue.js компоненти можна реєструвати глобально або локально:

1. Глобальна реєстрація – компонент доступний у всіх компонентах додатку:

```JavaScript
import { createApp } from 'vue'
import App from './App.vue'
import MyComponent from './components/MyComponent.vue'

const app = createApp(App)
app.component('MyComponent', MyComponent)
app.mount('#app')
```

2. Локальна реєстрація – компонент доступний тільки в межах конкретного
   компонента:

```JavaScript
import MyComponent from './components/MyComponent.vue'

export default {
  components: {
    MyComponent
  },
  template: `<MyComponent />`
}
```

#### Примітки:

- Глобальна реєстрація зручна для часто використовуваних компонентів.

- Локальна зменшує розмір бандлу при lazy loading.

</details>

<details>
<summary>54. Як працювати з даними, які не повинні бути реактивними, у Vue компоненті?</summary>

#### Vue.js

Для не реактивних даних у Vue можна:

1. Використовувати звичайні змінні в setup() (Composition API):

```JavaScript
setup() {
  let nonReactiveValue = 0

  function increment() {
    nonReactiveValue++
    console.log(nonReactiveValue) // оновлюється лише у консолі
  }

  return { increment }
}
```

2. shallowRef або ref без реактивності для об’єктів:

- shallowRef робить тільки саму змінну реактивною, а її властивості – ні.

3. Змінні поза data або reactive у Vue 2:

```JavaScript
export default {
  created() {
    this.nonReactive = 0
  }
}
```

- Vue не буде відслідковувати зміни this.nonReactive у шаблоні.

#### Примітка:

- Використовують для кешу, логів або даних, які не впливають на UI.

</details>

<details>
<summary>55. Що таке компоненти вищого порядку (Higher-Order Components) у Vue.js?</summary>

#### Vue.js

Компонент вищого порядку (HOC) — це функція, яка приймає компонент як аргумент і
повертає новий компонент з додатковою логікою або поведінкою. Використовується
для повторного використання логіки без зміни оригінального компонента.

#### Приклад (Vue 3, Composition API):

```JavaScript
// withLogger.js
export function withLogger(WrappedComponent) {
  return {
    setup(props, ctx) {
      console.log('Component rendered')
      return () => h(WrappedComponent, props, ctx.slots)
    }
  }
}

// Usage
import MyComponent from './MyComponent.vue'
import { withLogger } from './withLogger'

export default withLogger(MyComponent)
```

#### Особливості:

- HOC не змінює оригінальний компонент.

- Використовують для логування, авторизації, обробки помилок або повторного
  UI-поведінки.

</details>

<details>
<summary>56. Що таке реактивність у Vue.js і як вона працює?</summary>

#### Vue.js

Реактивність у Vue.js — це механізм, який автоматично оновлює DOM, коли
змінюються дані компоненту.

#### Як працює:

1. Vue обгортає дані (ref або reactive) у геттери/сеттери або проксі (Proxy у
   Vue 3).

2. Коли дані змінюються, Vue відслідковує залежності між даними і шаблоном.

3. DOM оновлюється лише для тих частин, які використовують змінені дані.

#### Приклад Vue 3:

```JavaScript
import { ref, reactive } from 'vue'

export default {
  setup() {
    const count = ref(0)
    const state = reactive({ message: 'Hello' })

    function increment() {
      count.value++
      state.message = 'Updated'
    }

    return { count, state, increment }
  }
}
```

#### Особливості:

- ref використовується для примітивів.

- reactive для об’єктів і масивів.

- Vue автоматично відслідковує залежності шаблону і ефективно перерендерює
  тільки потрібні частини.

</details>

<details>
<summary>57. Як реактивно додати нові властивості до Vue-інстансу або об’єкта, щоб Vue відслідковував їх зміни?</summary>

#### Vue.js

1. У Vue 2:

- Нові властивості об’єкта, створеного у data, не реактивні за замовчуванням.

- Використовують Vue.set або this.$set:

```JavaScript
data() {
  return {
    user: {}
  }
},
methods: {
  addAge() {
    this.$set(this.user, 'age', 25)
  }
}
```

2. У Vue 3:

- Використовують reactive або ref – нові властивості всередині reactive об’єкта
  автоматично реактивні:

```JavaScript
import { reactive } from 'vue'

setup() {
  const user = reactive({ name: 'Andriy' })
  user.age = 25 // реактивно, Vue 3 відслідковує зміни
  return { user }
}
```

#### Примітка:

- У Vue 3 більше не потрібно використовувати Vue.set.

- Для примітивів можна обгорнути у ref.

</details>

<details>
<summary>58. Що таке паттерн Observer у Vue.js і як він працює?</summary>

#### Vue.js

Vue.js використовує паттерн Observer (спостерігач) для реалізації реактивності.
Основна ідея: коли дані змінюються, усі “підписані” на ці дані компоненти або
шаблони автоматично оновлюються.

#### Як працює у Vue:

1. Vue обгортає data у геттери/сеттери (Vue 2) або Proxy (Vue 3).

2. Коли шаблон використовує властивість, Vue додає цей компонент у список
   “спостерігачів” цієї властивості.

3. При зміні властивості Vue повідомляє всіх спостерігачів і вони
   перерендерюються.

#### Схематично:

```
Data (Reactive)  --->  Observer List ---> Components update
```

#### Приклад Vue 3:

```JavaScript
import { reactive } from 'vue'

const state = reactive({ count: 0 })

function increment() {
  state.count++  // всі шаблони, що використовують state.count, автоматично оновляться
}
```

- Кожне поле об’єкта стає “спостережуваним”.

- Паттерн дозволяє Vue оновлювати тільки ті частини DOM, які залежать від
  змінних.

</details>

<details>
<summary>59. Яка роль класу Dep у системі реактивності Vue.js?</summary>

#### Vue.js

Dep (dependency) — це внутрішній клас у Vue 2, який реалізує паттерн Observer.
Він відповідає за відстеження залежностей і повідомлення “спостерігачів” про
зміни.

#### Основні моменти:

1. Кожна реактивна властивість має свій об’єкт Dep.

2. Коли компонент читає властивість, він підписується на Dep.

3. Коли властивість змінюється, Dep.notify() викликає оновлення всіх підписаних
   компонентів.

#### Схематично:

```
Reactive property → Dep → Watchers → Component re-render
```

#### Приклад концептуально:

```JavaScript
class Dep {
  constructor() {
    this.subscribers = new Set()
  }
  depend() {
    if (activeWatcher) this.subscribers.add(activeWatcher)
  }
  notify() {
    this.subscribers.forEach(sub => sub.update())
  }
}
```

#### Примітка:

- У Vue 3 механізм змінився на Proxy, і клас Dep більше не використовується
  напряму.

- У Vue 2 він критично важливий для реактивності data.

</details>

<details>
<summary>60. Як створити обчислювану властивість (computed) з сеттером у Vue.js?</summary>

#### Vue.js

У Vue можна створити computed з гетером і сеттером, щоб не тільки читати
значення, а й реагувати на його зміну.

#### Приклад (Vue 3, Composition API):

```JavaScript
import { ref, computed } from 'vue'

export default {
  setup() {
    const firstName = ref('Andriy')
    const lastName = ref('Motko')

    const fullName = computed({
      get() {
        return `${firstName.value} ${lastName.value}`
      },
      set(value) {
        const names = value.split(' ')
        firstName.value = names[0]
        lastName.value = names[1] || ''
      }
    })

    return { firstName, lastName, fullName }
  }
}
```

#### Особливості:

- **Getter** повертає обчислене значення.

- **Setter** дозволяє оновлювати залежні змінні при зміні computed.

- Використовується для двостороннього зв’язку (v-model) на computed.

</details>

<details>
<summary>61. Як Vue.js обробляє анімації та переходи (transitions)?</summary>

#### Vue.js

Vue.js має вбудовану систему для плавних вставок, видалень і зміни стану
елементів через компонент `<transition>` і `<transition-group>`.

#### Основні моменти:

1. `<transition>` – для одного елемента чи компонента.

2. `<transition-group>` – для списків і груп елементів.

3. Vue автоматично додає CSS-класи на різних етапах анімації:

- `v-enter`, `v-enter-active`, `v-enter-to`

- `v-leave`, `v-leave-active`, `v-leave-to`

#### Приклад:

```html
<template>
  <transition name="fade">
    <p v-if="show">Hello Vue!</p>
  </transition>
</template>

<script setup>
  import { ref } from 'vue';
  const show = ref(true);
</script>

<style>
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }
  .fade-enter-to,
  .fade-leave-from {
    opacity: 1;
  }
</style>
```

#### Особливості:

- Можна використовувати CSS-анімації або JavaScript hooks (beforeEnter, enter,
  leave тощо).

- `<transition-group>` додає анімацію для списків з ключами (key) для коректного
  відстеження елементів.

</details>

<details>
<summary>62. Як застосувати анімацію/переходи до списку елементів у Vue.js?</summary>

#### Vue.js

Для списків використовується компонент <transition-group>, який дозволяє
анімувати вставку, видалення або переміщення елементів у списку.

#### Приклад:

```html
<template>
  <button @click="addItem">Add Item</button>
  <transition-group name="list" tag="ul">
    <li v-for="item in items" :key="item.id">{{ item.text }}</li>
  </transition-group>
</template>

<script setup>
  import { ref } from 'vue';

  const items = ref([
    { id: 1, text: 'Item 1' },
    { id: 2, text: 'Item 2' },
  ]);

  function addItem() {
    const id = items.value.length + 1;
    items.value.push({ id, text: `Item ${id}` });
  }
</script>

<style>
  .list-enter-active,
  .list-leave-active {
    transition: all 0.5s;
  }
  .list-enter-from,
  .list-leave-to {
    opacity: 0;
    transform: translateY(20px);
  }
  .list-enter-to,
  .list-leave-from {
    opacity: 1;
    transform: translateY(0);
  }
</style>
```

#### Особливості:

- Кожен елемент повинен мати унікальний key.

- `<transition-group>` автоматично додає CSS-класи для етапів enter та leave.

- Можна анімувати позицію, opacity, масштаб або застосовувати
  JavaScript-анімації.

</details>

<details>
<summary>63. У чому різниця між CSS transitions і CSS animations?</summary>

#### Vue.js

| Властивість   | CSS Transitions                                 | CSS Animations                                         |
| ------------- | ----------------------------------------------- | ------------------------------------------------------ |
| Запуск        | Відбувається при зміні стану (hover, class, JS) | Запускається автоматично або через keyframes           |
| Контроль часу | Один раз на подію                               | Можна повторювати (infinite), задавати затримки, цикли |
| Гнучкість     | Обмежена: можна анімувати тільки кінцевий стан  | Висока: можна задавати проміжні стани через @keyframes |
| Складність    | Просте використання                             | Підходить для складних, багатоетапних анімацій         |

#### Приклад transition:

```css
button {
  transition: background-color 0.3s;
}

button:hover {
  background-color: red;
}
```

#### Приклад animation:

```css
@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

div {
  animation: bounce 1s infinite;
}
```

#### Коротко:

- **transition** – для простих ефектів при зміні стану;

- **animation** – для складних, циклічних анімацій.

</details>

<details>
<summary>64. Як створювати анімації за допомогою JavaScript у Vue.js?</summary>

#### Vue.js

У Vue.js можна використовувати JavaScript hooks у <transition> або
<transition-group>, замість CSS-класів. Це дозволяє анімувати властивості вручну
через JS.

#### Приклад (Vue 3, Composition API):

```html
<template>
  <button @click="show = !show">Toggle</button>
  <transition @before-enter="beforeEnter" @enter="enter" @leave="leave">
    <p v-if="show">Hello Vue!</p>
  </transition>
</template>

<script setup>
  import { ref } from 'vue';

  const show = ref(false);

  function beforeEnter(el) {
    el.style.opacity = 0;
    el.style.transform = 'translateY(-20px)';
  }

  function enter(el, done) {
    const animation = el.animate(
      [
        { opacity: 0, transform: 'translateY(-20px)' },
        { opacity: 1, transform: 'translateY(0)' },
      ],
      {
        duration: 500,
      }
    );
    animation.onfinish = done;
  }

  function leave(el, done) {
    const animation = el.animate(
      [
        { opacity: 1, transform: 'translateY(0)' },
        { opacity: 0, transform: 'translateY(-20px)' },
      ],
      { duration: 500 }
    );
    animation.onfinish = done;
  }
</script>
```

#### Особливості:

- `@before-enter`, `@enter`, `@leave` – основні хуки для JS-анімацій.

- `done` викликається після завершення анімації, щоб Vue завершив перехід.

- Можна використовувати **Web Animations API** або сторонні бібліотеки (GSAP,
  Anime.js).

</details>

<details>
<summary>65. Які JavaScript-хуки доступні у Vue.js для анімацій при вході і виході елемента?</summary>

#### Vue.js

У Vue.js для <transition> і <transition-group> доступні такі основні hooks для
входу та виходу:

**Hooks для входу (enter):**

- `before-enter` – перед початком входу, елемент ще не доданий у DOM

- `enter` – під час анімації входу

- `after-enter` – після завершення входу

- `enter-cancelled` – якщо анімація входу була скасована

**Hooks для виходу (leave):**

- `before-leave` – перед початком видалення елемента

- `leave` – під час анімації видалення

- `after-leave` – після завершення видалення

- `leave-cancelled` – якщо анімація видалення була скасована

**Приклад використання:**

```html
<transition
  @before-enter="beforeEnter"
  @enter="enter"
  @after-enter="afterEnter"
  @before-leave="beforeLeave"
  @leave="leave"
  @after-leave="afterLeave"
>
  <p v-if="show">Hello Vue!</p>
</transition>
```

- В JS-анімаціях обов’язково викликати `done()` у хук `enter/leave` після
  завершення анімації.

- Hooks дають повний контроль над анімацією елементів через JS.

</details>

<details>
<summary>66. Які найкращі практики організації коду у великих Vue.js додатках?</summary>

#### Vue.js

1. Структура папок:

- components/ – дрібні, повторно використовувані компоненти

- views/ – сторінки (для Vue Router)

- layouts/ – загальні макети

- store/ – Vuex/Pinia модулі

- services/ або api/ – запити до API

- composables/ – повторно використовувані Composition API функції

2. Компоненти:

- Використовувати локальну реєстрацію, коли компонент специфічний для певного
  модуля

- Дотримуватись “Smart vs Dumb components” (контейнерні компоненти управляють
  даними, презентаційні – відображення)

3. Повторне використання логіки:

- Використовувати composables замість mixins для Composition API

- Виносити утиліти в окремі файли

4. Стан додатку:

- Використовувати Pinia або Vuex для глобального стану

- Локальний стан зберігати у ref/reactive у компонентах

5. Lazy loading і code splitting:

- Динамічний імпорт для великих компонентів та маршрутів:

```JavaScript
const UserProfile = () => import('./views/UserProfile.vue')
```

6. Іменування:

- PascalCase для компонентів: UserCard.vue

- camelCase для методів і змінних у setup()

7. Стилі:

- Використовувати scoped CSS або CSS Modules

- Для глобальних змінних – variables.scss

8. Тестування:

- Юніт-тести для компонентів і composables

- E2E для критичних шляхів

</details>

<details>
<summary>67. Чому атрибут key важливий при рендерингу списків у Vue.js?</summary>

#### Vue.js

Атрибут key допомагає Vue ідентифікувати кожен елемент списку при оновленні DOM.
Це дозволяє ефективно перерендерювати тільки змінені елементи, а не весь список.

#### Основні моменти:

- Повинно бути унікальне значення для кожного елемента (id, наприклад).

- Без key Vue використовує “in-place patching”, що може призвести до
  неочікуваних перезаписів стану компонентів у списку.

- З key Vue застосовує diffing алгоритм оптимально і правильно відслідковує
  елементи.

#### Приклад:

```html
<ul>
  <li v-for="item in items" :key="item.id">{{ item.text }}</li>
</ul>
```

#### Рекомендація:

Використовувати стійкий і унікальний ідентифікатор, а не індекс масиву, особливо
якщо список може змінюватися.

</details>

<details>
<summary>68. Як структурувати компоненти у великому Vue.js додатку для масштабованості та підтримуваності?</summary>

#### Vue.js

1. Створювати ієрархію “глобальні → модульні → локальні”:

- `components`/ – маленькі повторно використовувані компоненти (кнопки, інпути)

- `modules`/`<module-name>`/`components`/ – компоненти специфічні для модуля

- `views`/ – сторінки для Vue Router

2. “Smart vs Dumb components” (Container / Presentational pattern):

- Контейнерні (Smart) – управляють даними, викликають API, обробляють логіку

- Презентаційні (Dumb) – отримують дані через props і рендерять UI

3. Компоненти за призначенням:

- Повторно використовувані UI-компоненти – маленькі, незалежні

- Вузькоспеціалізовані – для конкретного модуля або сторінки

4. Повторне використання логіки:

- Виносити функції у composables (Composition API)

- Використовувати mixins тільки у Vue 2

5. Файлова структура приклад:

```bash
src/
  components/      # глобальні UI-компоненти
  composables/     # повторно використовувана логіка
  modules/
    user/
      components/  # компоненти модуля
      views/
      store/       # модуль стану
  views/           # сторінки для маршрутизатора
  layouts/         # загальні макети
  services/        # API або утиліти
```

6. Іменування:

- PascalCase для компонентів: `UserCard.vue`

- camelCase для змінних і функцій у `setup()`

7. Lazy loading компонентів і маршрутів для швидкого завантаження.

</details>

<details>
<summary>69. Чому важливо уникати використання this у шаблонних виразах Vue.js?</summary>

#### Vue.js

1. У Vue 3 (Composition API) this не працює у шаблоні:

- В `setup()` немає контексту компонента, тому звертання через `this` призведе
  до помилки.

- Дані потрібно повертати з `setup()` і використовувати напряму:

```html
<template>
  <p>{{ count }}</p>
  <!-- правильно -->
  <!-- <p>{{ this.count }}</p> -- неправильно -->
</template>
<script setup>
  import { ref } from 'vue';
  const count = ref(0);
</script>
```

2. Vue 2 (Options API):

- `this` у шаблоні все ще працює, але не потрібно, бо шаблон автоматично
  прив’язаний до даних, props і computed.

- Використання `this` у шаблоні робить код менш чистим і зрозумілим.

3. Переваги уникання this:

- Чіткість коду

- Менше помилок при міграції на Composition API

- Легше тестувати компоненти

</details>

<details>
<summary>70. Як робити методи у Vue.js читаємими та компактними?</summary>

#### Vue.js

1. Розділяти логіку на невеликі функції:

- Замість одного великого методу робіть кілька маленьких допоміжних функцій у
  `methods` або `composables`.

2. Виносити повторювану логіку у composables або утиліти:

```JavaScript
// composables/useFormat.js
export function formatDate(date) {
  return new Date(date).toLocaleDateString()
}
```

3. Використовувати computed для похідних значень:

- Щоб не писати багато логіки у шаблоні або методах, обчислюйте значення у
  `computed`.

4. Структурувати методи за призначенням:

- Наприклад: `fetchData`, `handleClick`, `validateForm` – зрозумілі назви.

5. Використовувати async/await для асинхронних операцій:

- Код легше читати, ніж через `.then()`/`.catch()`.

6. Коментувати лише складні ділянки логіки:

- Не варто коментувати очевидні речі, щоб не перевантажувати методи.

</details>

<details>
<summary>71. Як писати юніт-тести для Vue.js компонентів?</summary>

#### Vue.js

1. **Інструменти:**

- Vue Test Utils – офіційна бібліотека для рендерингу компонентів

- Jest / Vitest – тестовий раннер

2. **Основні кроки:**

- Імпортувати компонент

- Відрендерити його у тестовому середовищі (mount або shallowMount)

- Перевірити рендеринг, реактивність, події та computed

3. **Приклад (Vue 3 + Vitest + Vue Test Utils):**

```JavaScript
import { mount } from '@vue/test-utils'
import { describe, it, expect } from 'vitest'
import Counter from '../Counter.vue'

describe('Counter.vue', () => {
  it('renders initial count', () => {
    const wrapper = mount(Counter)
    expect(wrapper.text()).toContain('Count: 0')
  })

  it('increments count when button is clicked', async () => {
    const wrapper = mount(Counter)
    await wrapper.find('button').trigger('click')
    expect(wrapper.text()).toContain('Count: 1')
  })
})
```

4. **Поради:**

- Використовувати shallowMount для ізоляції компонентів

- Тестувати props, events, computed і методи

- Для асинхронних операцій – await nextTick()

</details>

<details>
<summary>72. Які фреймворки для тестування зазвичай використовують з Vue.js?</summary>

#### Vue.js

1. **Vue Test Utils** – офіційна бібліотека для юніт-тестування компонентів Vue.

2. **Jest** – популярний тестовий раннер для юніт і snapshot-тестів.

3. **Vitest** – сучасний альтернативний раннер, швидший, добре інтегрується з
   Vue 3 + Vite.

4. **Cypress** – для E2E-тестування, симуляція користувацької взаємодії у
   браузері.

5. **Playwright** – альтернатива Cypress для E2E-тестів з кросбраузерною
   підтримкою.

6. **Testing Library (Vue Testing Library)** – робить тести більш
   “user-centric”, перевіряючи UI так, як його бачить користувач.

#### Порада:

- Юніт-тести → Jest / Vitest + Vue Test Utils

- E2E → Cypress або Playwright

</details>

<details>
<summary>73. Які найкращі способи відлагодження Vue.js додатку?</summary>

#### Vue.js

1. **Vue DevTools (Chrome/Firefox):**

- Перегляд структури компонентів, стану data, props, computed, Vuex/Pinia.

- Можна відслідковувати реактивність і події.

2. **Консольні логи:**

- console.log, console.warn, console.error – для швидкої перевірки значень.

- Використовувати у setup(), методах та lifecycle hooks.

3. **Debugger:**

- Вставка debugger у коді з відкритим DevTools дозволяє зупинити виконання і
  досліджувати стан.

4. **Використання Watchers:**

- Для відслідковування змін даних і виявлення проблем з реактивністю.

```JavaScript
watch(count, (newVal) => console.log('count changed:', newVal))
```

5. **Відлагодження Vuex/Pinia:**

- Vue DevTools показує всі мутації та дії, що допомагає зрозуміти потік даних.

6. **Error Boundaries (Vue 3):**

- Використовувати `<ErrorBoundary>` або errorCaptured для відлову помилок у
  компонентах.

7. **Source Maps:**

- Для відлагодження TypeScript або скомпільованого коду використовуйте source
  maps у DevTools.

8. **Unit & E2E тести:**

- Автоматичне виявлення помилок під час розробки через Jest/Vitest та
  Cypress/Playwright.

</details>

<details>
<summary>74. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>75. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>76. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>77. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>78. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>79. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>80. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>81. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>82. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>83. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>84. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>85. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>86. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>87. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>88. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>89. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>90. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>91. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>92. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>93. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>94. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>95. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>96. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>97. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>98. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>99. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>100. ???</summary>

#### Vue.js

- Coming soon...😎

</details>

<details>
<summary>101. ???</summary>

#### Vue.js

- Coming soon...😎

</details>
