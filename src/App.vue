<template>
  <div id="app">
    <div class="wrapper mr-4">
      <header>
        <div class="parent-header">
          <h1 class="font-weight-bold text-dark">{{h1}}</h1>
          <p class="text-dark parent-header__paragraph"> {{subtitle}}</p>
        </div>
      </header>
      <main>

        <div class="parent-edit-delete d-flex justify-content-end">
          <button @click="EditListCase" type="button"
            class="button-main button-main_filled-purple btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 text-uppercase">{{EditButtonVaule}}</button>

          <button @click="ToRemoveTheCase" type="button"
            class="button-main button-main_filled-orange btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 ml-2 text-uppercase">{{DeleteButtonVaule}}</button>
        </div>

        <div class="parent-list-cases">
          <ul>
            <li class="parent-list-cases__list-case font-weight-bold text-dark"
              v-for="(task, index) in arrayListCases" :key="index">{{index + 1}}.
              {{task.title}}
              <hr>
            </li>
          </ul>
        </div>

        <div class="parent-add-cases mt-3">
          <button v-on:click="addCases" type="button"
            class="parent-add-cases__button button-main_filled-purple btn btn-primary rounded-pill d-flex justify-content-center align-items-center font-weight-bold border-0 text-uppercase">{{ButtonValue}}</button>
        </div>
      </main>
    </div>

    <div v-if="BoolValueClick" class="parent-write-block shadow-lg p-4">
      <h3 class="font-weight-bold text-dark">{{headline}}</h3>
      <form action="#">
        <input v-model="inputCase" class="parent-write-block__input form-control" type="text"
          placeholder="Побегать вечером">
        <button @click="saveCase" type="submit"
          class="parent-write-block__button btn text-uppercase mt-4">{{seveButton}}</button>
      </form>
    </div>

  </div>
</template>

<script>
  export default {
    name: 'App',
    components: {},

    data() {
      return {
        seen: true,
        mes: 'helloworld',
        h1: "Список дел",
        subtitle: 'Добавляйте и редактируйте списки дел',
        EditButtonVaule: 'Изменить',
        DeleteButtonVaule: 'Удалить',
        ButtonValue: 'Добавить дело',
        BoolValueClick: false,
        headline: 'Что нужно сделать ?',
        seveButton: 'Сохранить',
        inputCase: '',
        valueRemoveButton: 'Remove',
        visibilityButtonRemove: false,
        QuestionForRemove: '',
        QuestionForEdit: '',
        arrayListCases: [{
            title: 'Выучить Vue.js'
          },
          {
            title: 'Прогуляться'
          },
        ],
      }
    },
    methods: {
      show_bool(data) {
        console.log('show me message', data)
      },
      addCases() {
        this.BoolValueClick = true
      },
      saveCase() {
        this.BoolValueClick = false
        this.arrayListCases.push({
          title: this.inputCase
        })
        this.inputCase = ''
      },
      ToRemoveTheCase() {
        this.QuestionForRemove = +prompt('Какую задачу вы ходите удалить ? Введите число', 1)
        this.arrayListCases.splice(this.QuestionForRemove - 1, 1)
      },
      EditListCase(){
        this.QuestionForEdit = +prompt('Какую задачу вы ходите изменить ? Введите число', 1)
        this.arrayListCases[this.QuestionForEdit -1].title = prompt('Текст задачи', 'Выбросить мусор')
        
      }
    }
  }
</script>

<style lang="scss">
  $fill_purple:#BB6BD9;
  $fill_orange:#EB5757;

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
  }

  ul {
    list-style: none;
  }

  .parent-list-cases__list-case {
    position: relative;
  }

  .parent-list-cases__remove-button {
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
  }

  .parent-add-cases__button {
    width: 139px;
    height: 44px;
    font-size: 12px;
  }


  .button-main_filled-purple,
  .button-main_filled-purple:focus {
    background-color: $fill_purple;
  }

  .button-main {
    width: 105px;
    height: 33px;
    font-size: 9px;
  }

  .button-main_filled-orange,
  .button-main_filled-orange:focus {
    background-color: $fill_orange
  }

  .wrapper {
    width: 40%;
    height: calc(100vh - 40px);
    box-sizing: border-box;
  }

  h1 {
    font-size: 48px;
  }

  .parent-header__paragraph {
    font-size: 14px;
  }

  .parent-write-block {
    width: 57%;
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
    color: $fill_purple;
  }

  .parent-write-block__button:hover {
    color: $fill_purple;
    background-color: #bc6bd923;
  }

  .parent-write-block__button:active {
    box-shadow: 0 0 10px 2px $fill_purple;
  }
</style>