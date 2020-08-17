<template>
    <div class="parent-write-block shadow-lg p-4">
        <h3 class="font-weight-bold text-dark">{{headline}}</h3>
        <input class="parent-write-block__input form-control" type="text" placeholder="Побегать вечером">
        <button type="button" class="parent-write-block__button btn text-uppercase mt-4">{{seveButton}}</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                headline: 'Что нужно сделать ?',
                seveButton: 'Сохранить'
            }
        },
    }
</script>

<style lang="scss" scoped>
    .parent-write-block {
        width: 59vw;
        height: calc(100vh - 40px);
    }

    h3 {
        font-size: 12px;
    }

    .parent-write-block__input {
        background: #FFFFFF;
        border: 1px solid rgba(31, 32, 65, 0.25);
        box-sizing: border-box;
        border-radius: 4px;

        max-width: 320px;
        height: 44px;
    }

    .parent-write-block__input::placeholder {
        font-size: 14px;
        opacity: 0.25;
    }

    .parent-write-block__button {
        width: 114.35px;
        height: 36px;
        background: #FFFFFF;
        border: 1px solid #DBDBDB;
        border-radius: 2px;

        font-weight: 500;
        font-size: 14px;
        line-height: 16px;
        color: #BB6BD9;
    }

    .parent-write-block__button:hover {
        color: #BB6BD9;
        background-color: #bc6bd923;
    }

    .parent-write-block__button:active {
        box-shadow: 0 0 10px 2px #BB6BD9;

    }
</style>