# v-Generic-Form-vue2

#### Installing

Using npm: 

```
npm i v-generic-form-vue2
```

Using yarn: 

```
yarn add v-generic-form-vue2
```

#### Getting Started

We need to import these files in order to use this plug-in :

```js
import Vue from "vue";
import vGenericForm from "v-generic-form-vue2";

Vue.use(vGenericForm);
```

##### Basic Example :

```jsx
<template>
  <div>
    <v-generic-form
      :fields="fields"
      :onSubmit="onSubmit"
      :onDataChange="onDataChange"
    />
  </div>
</template>

<script>
import Vue from "vue";
import vGenericForm from "v-generic-form-vue2";

Vue.use(vGenericForm);

export default {
  name: "Form",
  computed: {
    fields() {
      return [
        {
          name: "input",
          placeholder: "input",
          label: "input label",
          type: "text",
        }
      ];
    },
  },
  methods: {
    onSubmit(data) {
      console.log(data);
    },
    onDataChange(data) {
      console.log(data);
    },
  },
};
</script>
```
