<template>
  <div class="clock">
      <div class="dcell">
        {{ time.hours }} 
      </div>
      <div class="dcell">
        :
      </div>
      <div class="dcell">
        {{ time.minutes }} 
      </div>
      <div class="dcell">
        :
      </div>
      <div class="dcell">
        {{ time.seconds }} 
      </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class Clock extends Vue {
    pad(num: number): string {
      return (num == 0) ? '00' : (num < 10) ? '0' + num.toString() : num.toString();
    }
    private time = {
      seconds:this.pad(new Date().getSeconds()),
      minutes:this.pad(new Date().getMinutes()),
      hours:this.pad(new Date().getHours()),
    }

    created () {
      setInterval(() => this.time.seconds = this.pad(new Date().getSeconds()), 1000)
      setInterval(() => this.time.minutes = this.pad(new Date().getMinutes()), 1000 * 60)
      setInterval(() => this.time.hours = this.pad(new Date().getHours()), 1000 * 60 * 60)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dcell {
    display: inline-block;
}

.clock {
    font-size: 7rem;
    font-family: "Roboto Mono";
}
</style>
