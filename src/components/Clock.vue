    <template>
      <div class="clock">
        <div><h3>Digital Clock</h3></div>
        <div v-if="local">{{ local }}</div>
      </div>
    </template>
<script>
export default {
  name: "DigitalClock",
  data() {
    return {
      local: null
    }
  },
  beforeMount() {
    this.setTime()
  },
  mounted() {
    setInterval(() => this.setTime(), 1000)
  },
  methods: {
    setTime() {
      const date = new Date();
      let local = date.toLocaleTimeString()
      this.local = local
    }
  }
}
</script>


<style scoped>
.clock {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    background-color: grey;
    margin: 10px auto;
    display: flex;
    flex-flow: column;
    justify-content: center;
    color: navy;
}
</style>