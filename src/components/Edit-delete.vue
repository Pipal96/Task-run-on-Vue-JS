<template>
    <div class="parent-edit-delete d-flex justify-content-end">
        <button type="button"
            class="button-main button-main_filled-purple btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 text-uppercase">{{EditButtonVaule}}</button>

        <button type="button"
            class="button-main button-main_filled-orange btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 ml-2 text-uppercase">{{DeleteButtonVaule}}</button>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                EditButtonVaule: 'Изменить',
                DeleteButtonVaule: 'Удалить',
                
            }
        },
    }
</script>

<style lang="scss" scoped>
    $fill_purple:#BB6BD9;
    $fill_orange:#EB5757;

    .button-main {
        width: 105px;
        height: 33px;
        font-size: 9px;
    }

    .button-main_filled-purple {
        background-color: $fill_purple;
    }
    .button-main_filled-orange {
        background-color: $fill_orange
    }
</style>