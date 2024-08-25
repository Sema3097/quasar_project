<template>
  <q-page class="flex flex-center">
    <main class="text-weight-medium" style="padding: 0 100px">
      <ol style="display: flex; flex-direction: column; gap: 20px">
        <li>Поднять проект на VUE, подключить quasar;</li>
        <li>
          Главная страница - приветствие, в шапке ниспадающее меню (переход на 2
          страницы + на главную);
        </li>
        <li>
          Страница1 - форма из минимум 3х полей(дата, текст, select), данные из
          которой отправляются на сервер при нажатии кнопки сохранить (post
          запрос через axios, можно просто на localhost, ответ не нужен);
        </li>
        <li>Страница2 - Текст тестового задания.</li>
      </ol>
    </main>
  </q-page>
</template>

<script setup>
defineOptions({
  name: "SecondPage",
});
</script>

<style></style>
