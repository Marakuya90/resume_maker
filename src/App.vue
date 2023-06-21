<template>
  <div class="container mt-5">
    <div class="d-flex justify-content-between gap-3 mb-3 ps-3">
      <form class="form_size" @submit.prevent="post">
        <div class="form-control d-flex flex-column pb-4 mb-3">
          <div class=" d-flex flex-column mb-3 ">
            <label for="type">Тип блока</label>
            <select id="type" class="form-select" v-model="type">
              <option value="title">Заголовок</option>
              <option value="subtitle">Подзаголовок</option>
              <option value="foto">Аватар</option>
              <option value="text">Текст</option>
            </select>
          </div>
          <div class="d-flex flex-column">
            <label for="content">Значение</label>
            <textarea id="content" class="form-control" v-model="content"></textarea>
          </div>
        </div>
        <button class="btn btn-info" :disabled="!validationDesc">Добавить</button>
      </form>
      <div class="container form-control d-flex pt-4 flex-column align-items-center">
        <h2 v-if="resume.length === 0">Добавьте первый блок, чтобы увидеть результат</h2>
        <div v-for="item in resume" :key="item.content">
          <app-title
              v-if="item.type === 'title'"
              :title = "item.content"
          ></app-title>
          <app-sub-title
              v-if="item.type === 'subtitle'"
              :title="item.content"
          ></app-sub-title>
          <app-foto
              v-if="item.type === 'foto'"
              :foto="item.content"
          ></app-foto>
          <app-text
              v-if="item.type === 'text'"
              :text="item.content"
          ></app-text>
        </div>

      </div>
    </div>
    <button class="btn btn-primary">Загрузить комментарии</button>
  </div>
</template>

<script>
  import AppTitle from "@/components/AppTitle.vue";
  import AppSubTitle from "@/components/AppSubTitle.vue";
  import AppFoto from "@/components/AppFoto.vue";
  import AppText from "@/components/AppText.vue";
  export default {
    name: 'App',
    components: { AppTitle, AppSubTitle, AppFoto, AppText },
    methods: {
      post() {
        this.resume.push({type: this.type,
          content: this.content
        })
        this.type = 'title',
        this.content = ''
        console.log(this.resume)
      }
    },
    data() {
      return {
        type: 'title',
        content: '',
        resume:[]
        }
      },
    computed: {
        validationDesc() {
          return this.content.length > 4
        }
      }
    }

</script>

<style scoped>
#app {

  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.resume {
  height: 100px;
  width: 100px;
}
.form_size {
  width: 40%;
}
</style>
