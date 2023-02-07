<script>
import { store } from '../../store.js';

export default {
  name: 'SectionCard',
  data() {
    return {
      store,
    }
  },

}
</script>

<template> 
  <div>
    <select class="form-select" aria-label="Default select example" v-model="store.selectValue" @change="$emit('search')">
      <option selected value="">Select by Archetype</option>
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
