<template>
   
  <a-form
    :form="form"
    @submit="handleSubmit"
  >
    <h2> 预约取件</h2>
    <a-form-item
      label="运单号"
      :label-col="{ span: 5 }"
      :wrapper-col="{ span: 12 }"
    >
      <a-input
        v-decorator="[
          '运单号',
          {rules: [{ required: true, message: 'Please input your note!' }]}
        ]"
      />
    </a-form-item>
    <a-form-item
      label="取件时间"
      :label-col="{ span: 5 }"
      :wrapper-col="{ span: 12 }"
    >
      <a-input
        v-decorator="[
          '取件时间',
          {rules: [{ required: true, message: 'Please input your note!' }]}
        ]"
      />
    </a-form-item>
  </a-form>
</template>

<script>
export default {
  data () {
    return {
      formLayout: 'horizontal',
      form: this.$form.createForm(this),
    };
  },
  methods: {
    handleSubmit (e) {
      e.preventDefault();
      this.form.validateFields((err, values) => {
        if (!err) {
          console.log('Received values of form: ', values);
        }
      });
    }
  },
};
</script>