<template>
  <q-list class="text-secondary">
    <div v-for="(menu, index) in menus" :key="index">
      <q-item
        v-if="menu.childrens.length <= 0"
        :class="{ bordered: menu.id === idSelecionado }"
        @click="selecionarId(menu.id)"
        clickable
        dense
      >
        <q-item-section v-if="menu.icon" avatar>
          <q-icon :name="menu.icon" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ menu.title }}</q-item-label>
        </q-item-section>
      </q-item>
      <q-expansion-item
        v-else
        dense
        dense-toggle
        expand-separator
        :icon="menu.icon"
        :label="menu.title"
        :content-inset-level="1"
      >
        <q-list>
          <q-item
            v-for="children in menu.childrens"
            :key="children.title"
            :class="{ bordered: children.id === idSelecionado }"
            @click="selecionarId(children.id)"
            clickable
            dense
          >
            <q-item-section avatar>
              <q-icon :name="children.icon" />
            </q-item-section>
            <q-item-section>
              <q-item-label
                ><span class="white-text">{{
                  children.title
                }}</span></q-item-label
              >
            </q-item-section>
          </q-item>
        </q-list>
      </q-expansion-item>
    </div>
  </q-list>
</template>

<script>
export default {
  data() {
    return {
      idSelecionado: 0,
      menus: [
        {
          id: 1,
          path: '/home',
          title: 'Página incial',
          icon: 'home',
          childrens: [],
        },
        {
          path: '/comercial',
          title: 'Comercial',
          icon: 'shopping_cart',
          childrens: [
            {
              id: 2,
              path: '/comercial/clientes',
              title: 'Clientes',
              icon: 'people_outline',
            },
          ],
        },
      ],
    };
  },
  methods: {
    selecionarId(id) {
      this.idSelecionado = id;
    },
  },
};
</script>

<style>
.bordered {
  border: 2px solid var(--secundary-color);
}
.q-expansion-item.expanded {
  border: 1px solid yellow;
}
</style>
