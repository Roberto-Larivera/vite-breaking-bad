<script>
import { store } from '../../store.js';

export default {
  name: 'SectionCard',
  data() {
    return {
      store,
    }
  },
  // props:{
  //   myNumber:{
  //     type: Number,
  //     default: 0
  //   }
  // }

}
</script>

<template>
  <div>
    <select class="form-select" aria-label="Default select example">
      <option selected disabled>Select by Archetype</option>
      <option value="">None</option>
      <option :value="element.archetype_name" v-for="element in store.listArchetype">{{element.archetype_name}}</option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
// .form-select{
//   option{
//     text-transform: uppercase;
//   }
// }
</style>
