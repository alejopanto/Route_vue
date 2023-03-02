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
          <Action @create="create" />
        </template>
      </Resume>
    </template>
    <template #movements>
      <Movements :movements="movements" @remove="remove" />
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
      movements: [
        {
          id: 0,
          title: "Movimiento 1",
          description: "Una descripcion sin mucho sabor",
          amount: 100,
          time: new Date("02-01-2023"),
        },
        {
          id: 1,
          title: "Movimiento 2",
          description: "Una descripcion sin mucho sabor",
          amount: 200,
          time: new Date("02-01-2023"),
        },
        {
          id: 2,
          title: "Movimiento 3",
          description: "Una descripcion sin mucho sabor",
          amount: 500,
          time: new Date("02-01-2023"),
        },
        {
          id: 3,
          title: "Movimiento 4",
          description: "Una descripcion sin mucho sabor",
          amount: 200,
          time: new Date("02-01-2023"),
        },
        {
          id: 4,
          title: "Movimiento 5",
          description: "Una descripcion sin mucho sabor",
          amount: -400,
          time: new Date("02-01-2023"),
        },
        {
          id: 5,
          title: "Movimiento 6",
          description: "Una descripcion sin mucho sabor",
          amount: -600,
          time: new Date("02-01-2023"),
        },
        {
          id: 6,
          title: "Movimiento 7",
          description: "Una descripcion sin mucho sabor",
          amount: -300,
          time: new Date("02-01-2023"),
        },
        {
          id: 7,
          title: "Movimiento 8",
          description: "Una descripcion sin mucho sabor",
          amount: 0,
          time: new Date("02-01-2023"),
        },
        {
          id: 8,
          title: "Movimiento 9",
          description: "Una descripcion sin mucho sabor",
          amount: 300,
          time: new Date("01-01-2023"),
        },
        {
          id: 9,
          title: "Movimiento 10",
          description: "Una descripcion sin mucho sabor",
          amount: 500,
          time: new Date("01-01-2023"),
        },
      ],
    };
  },
  computed: {
    amounts() {
      const lastDays = this.movements
        .filter((m) => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);
          return m.time > oldDate;
        })
        .map((m) => m.amount);

      return lastDays.map((m, i) => {
        const lastMovements = lastDays.slice(0, i);

        return lastMovements.reduce((suma, movement) => {
          return suma + movement;
        }, 0);
      });
    },
  },

  methods: {
    create(movement) {
      this.movements.push(movement);
    },
    remove(id) {
      const indexMv = this.movements.findIndex((m) => m.id === id);
      this.movements.splice(indexMv, 1);
    },
  },
};
</script>
