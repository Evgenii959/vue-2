<template>
  <div class="container">
    <div class="block">
      <div>
        <h1>Информация о себе:</h1>
        <div v-for="(fieldValue, fieldLabel, index) in formFields" :key="index">
          <label :for="fieldLabel">{{ fieldLabel }}:</label>
          <input :id="fieldLabel" v-model="formFields[fieldLabel]" />
        </div>
        <button>Сохранить</button>
      </div>
      <div>
        <h2>Предпросмотр:</h2>
        <p v-for="(fieldValue, fieldLabel, index) in formFields" :key="index">
          {{ `${fieldLabel}: ${fieldValue}` }}
        </p>
      </div>
    </div>
    <div>
      <h3 for="additionalField">Доболнительное поле</h3>
      <input id="additionalField" v-model="additionalField" />
      <button type='submit' @click="addNewField">Добавить</button>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      formFields: {
        firstName: '',
        secondName: '',
        thirdName: '',
      },
      additionalField: '',
    };
  },
  methods: {
    addNewField() {
      this.$set(this.formFields, this.additionalField)
    },
  },
};
</script>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  gap: 50px;
}
.block {
  display: flex;
  gap: 50px;
}
</style>
