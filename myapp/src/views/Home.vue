<template>
  <div class="home">
    <p v-if="visible">Maintenant vous me voyez {{message}}</p>
    <button v-on:click="foo()">
      ok
    </button>
     <div v-background>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</div>
    <div v-background="green">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua</div>
    <Todos />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Todos from '@/components/todos.vue';
import { Background } from '@/directives/background.directive';
@Component({
  components: {
    Todos,
  },
  directives:{
    Background
  }
})
export default class Home extends Vue {

    message= 'test';
    visible = true;
    foo(){
      this.visible = !this.visible;
    }
}
</script>