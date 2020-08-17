<template>
    <div class="parent-add-cases mt-3">
        <button v-on:click="addCases" type="button"
            class="button-main button-main_filled-purple btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 text-uppercase">{{ButtonValue}}</button>
            <p v-if="BoolValueClick">test</p>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                ButtonValue: 'Добавить дело',
                BoolValueClick: false,
            }
        },
        methods: {
            addCases() {
                if (this.BoolValueClick == false) {
                    this.BoolValueClick = true
                    this.$emit('value_click', this.BoolValueClick)
                }
            }
        },
    }
</script>

<style lang="scss" scoped>
    $fill_purple:#BB6BD9;

    .button-main {
        width: 139px;
        height: 44px;
        font-size: 12px;
    }

    .button-main_filled-purple {
        background-color: $fill_purple;
    }
</style>