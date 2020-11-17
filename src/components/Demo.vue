<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="row">
      <div class="col-sm-6">
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          <b-form-group
              id="input-group-1"
              label="Задача"
              label-for="input-1"
              description="Введите задачу,которую надо добавить"
          >
            <b-form-input
                id="input-1"
                v-model="form.task"
                type="text"
                required
                placeholder="Помыть посуду"
            ></b-form-input>
          </b-form-group>
          <b-button type="submit" variant="primary">Добавить</b-button>
          <b-button type="reset" variant="danger">Очистить</b-button>
        </b-form>
        <b-card class="mt-3" header="Панель для отладки">
          <pre class="m-0">{{ form }}</pre>
        </b-card>
      </div>
      <div class="col-sm-6">
        <b-card class="mt-3" header="Список задач:">
<!--          Здесь должен быть массив. А задача должны в него добавляться-->
          <b-list-group>
            <b-list-group-item>Задача 1</b-list-group-item>
            <b-list-group-item> Задача 2</b-list-group-item>
          </b-list-group>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  props: {
    msg: String
  },
  data() {
    return {
      form: {
        task: '',
      },
      show: true
    }
  },
  methods: {
    onSubmit() {
      alert(JSON.stringify(this.form)) // Выводит содержимое формы в окне alert
    },
    onReset() {
      // Reset our form values
      this.form.task = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
