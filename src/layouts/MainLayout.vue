<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn color="primary" label="Menu" style="margin: 0 auto">
          <q-menu transition-show="scale" transition-hide="scale">
            <q-list style="min-width: 100px">
              <q-item clickable to="/">
                <q-item-section>Home Page</q-item-section>
              </q-item>
              <q-item clickable to="firstpage">
                <q-item-section>First Page</q-item-section>
              </q-item>
              <q-separator />
              <q-item clickable to="secondpage">
                <q-item-section>Second Page</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
defineOptions({
  name: "MainLayout",
});
</script>
