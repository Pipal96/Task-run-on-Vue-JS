<template>
    <div class="parent-header">
        <h1 class="font-weight-bold text-dark">{{h1}}</h1>
        <p class="text-dark parent-header__paragraph"> {{subtitle}}</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                h1: "Список дел",
                subtitle: 'Добавляйте и редактируйте списки дел',
            }
        },
    }
</script>

<style lang="scss" scoped>
h1 {
    font-size: 48px;
}
.parent-header__paragraph {
    font-size: 14px;
}
</style>