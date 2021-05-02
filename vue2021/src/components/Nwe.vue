<template>
    <div>
        <button @click="clickme()">Click Me</button>
        <textarea name="" id="" cols="30" rows="10"></textarea>
    </div>
</template>

<script>
export default {
    name: "Nwe",
    components: {},
    props: ["title"],
    methods: {
        clickme() {
            console.log("Clicked!");
        },
    },
};
</script>

<style></style>
