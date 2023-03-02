<template>
  <Layout>
    <template #header>
      <Header></Header>
    </template>
    <template #resume>
      <Resume
        :total-label="'Ahorro total'"
        :label="label"
        :total-amount="20876897"
        :amount="amount"
      >
        <template #graphic>
          <Graphic :amounts="amounts" />
        </template>
        <template #action>
          <Action />
        </template>
      </Resume>
    </template>
    <template #movements>
      <Movements :movements="movements" />
    </template>
  </Layout>
</template>

<script>
import Layout from "./Layout.vue";
import Header from "./Header.vue";
import Resume from "./Resume/Index.vue";
import Action from "./Action.vue";
import Movements from "./Movements/Index.vue";
import Graphic from "./Resume/Graphic.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Action,
    Movements,
    Graphic,
  },

  data() {
    return {
      label: null,
      amount: null,
      amounts: [100, 200, 500, 200, -400, -600, -300, 0, 300, 500],
      movements: [
        {
          id: 0,
          title: "Movimiento 1",
          description: "Una descripcion sin mucho sabor",
          amount: 123456,
        },
        {
          id: 1,
          title: "Movimiento 2",
          description: "Una descripcion sin mucho sabor",
          amount: -123456,
        },
        {
          id: 2,
          title: "Movimiento 3",
          description: "Una descripcion sin mucho sabor",
          amount: 123456,
        },
        {
          id: 3,
          title: "Movimiento 4",
          description: "Una descripcion sin mucho sabor",
          amount: -123456,
        },
        {
          id: 4,
          title: "Movimiento 5",
          description: "Una descripcion sin mucho sabor",
          amount: 123456,
        },
      ],
    };
  },
};
</script>
