# v-generic-form-vue2

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

#### Adding validation

> v-generic-form-vue2 uses **_[validate.js](https://validatejs.org/)_** behind the scenes for validation so refer to it for adding custom rules or finding all available validators.

Validation is as simple as passing a rules object to the field in your schema.

```js
fields() {
      return [
        {
          name: "input 1",
          placeholder: "input 1",
          label: "input label",
          type: "text",
          rules: {
            required: true,
            exclusion: {
              within: [1, 5],
              message: "^We don't support %{value} right now, sorry",
            },
          },
        },
      ];
    },
```
