<template>
  <div id="app">
    <h1><u>Cuenta Regresiva</u></h1>
    
    <img class="group timerImg" src="https://miro.medium.com/max/512/1*EmGD7Z4rUiD0RFebPvXJQw.png" alt="">

    <div>
      <div class="group">
        <button class="timerButton" @click="startCountdown(2)">2s</button>
        <button class="timerButton" @click="startCountdown(3)">3s</button>
        <button class="timerButton" @click="startCountdown(5)">5s</button>
        <button class="timerButton" @click="startCountdown(7)">7s</button>
        <button class="timerButton" @click="startCountdown(11)">11s</button>
        <button class="timerButton" @click="startCountdown(13)">13s</button>
      </div>
      <div class="group">
        <label>Ingresa tu propio temporizador:</label>
        <input type="number" placeholder="Ingresa aqui!" v-model="myTimer">
        <button @click="startCountdown(myTimer)">Go!</button>
      </div>
    </div>
    <h1>{{ countdown }}</h1>
  </div>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        myTimer: '',
        countdown: '',
      }
    },
    methods: {
      startCountdown(time) {
        let thisTimer = time
        const settingInterval = setInterval(() => {
          console.log(thisTimer)
          thisTimer--
          this.countdown = `${thisTimer}s`
          if (thisTimer === 0) {
            clearInterval(settingInterval)

          }
        }, 1000);
      }
    },
  }
</script>

<style>
*{
  text-align: center;
}

.group{
  margin: 20px 0;
}
.timerImg{
  width: 100px;
}
.timerButton{
  width: 60px;
}
</style>