<template>
    <Layout>
        <template #header>
            <Header></Header>
        </template>
        <template #resume>
            <Resume :label="'Ahorro total'" :date="date" :amount="amount" :total-amount="2000">
                <template #graphic>
                    graphic
                </template>
                <template #action>
                    <Action :label="'Agregar movimiento'" @click="$emit('add')"></Action>
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
import Resume from "./Resume/index.vue";
import Movements from "./Movements/index.vue";
import Action from "./Action.vue";
export default {
    components: {
        Layout,
        Header,
        Resume,
        Movements,
        Action,
    },
    data() {
        return {
            amount: 1000,
            date: "26 de noviembre del 2022",
            movements: [
                {
                    id: 1,
                    title: "Movimiento",
                    description: "Deposito de salario",
                    amount: "1000",
                },
                {
                    id: 2,
                    title: "Movimiento 1",
                    description: "Deposito de honorarios",
                    amount: "500",
                },
                {
                    id: 3,
                    title: "Movimiento 3",
                    description: "Comida",
                    amount: "-100",
                },
                {
                    id: 4,
                    title: "Movimiento 4",
                    description: "Colegiatura",
                    amount: "1000",
                },
                {
                    id: 5,
                    title: "Movimiento 5",
                    description: "Reparación equipo",
                    amount: "1000",
                },
            ],
        };
    }
};
</script>
