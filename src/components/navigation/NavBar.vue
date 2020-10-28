<template>
    <div>
        <a href="#" @click="selectComponent('cour-list')"></a>
        <a href="#" @click="selectComponent('cour-list')"></a>
    </div>
</template>

<script>
export default {
    name: "nav-bar",
    data() {
        return {
            navigation: [
                { name: "tous les cours", component: "cour-list" },
                { name: "MA selection", component: "cour-list" },
            ]
        }
    },
methods: {
    selectedComponent(comp) {
        this.$emit('change-component', comp)
    }
}
}
</script>