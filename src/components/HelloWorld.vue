<template>
  <div class="hello">
    
    <div class="th-box">
      <div class="temp">
        <p class="">
            Temperature
          <img :src="Timg" alt="Temperature" style="width: 48px;" />
        </p>
        <p @click="TextSwitch" class="TextSize hoverText">{{text}}</p>   
      </div>
  
      <div class="humn">
        <p>
          Humidity
          <img :src="Himg" alt="Humidity" style="width: 48px;" />
        </p>
        <p class="TextSize">51%</p>
      </div>
    </div>
  </div>
<!-- ----------------------------------------------------- -->
  <div class="hello ">
    <div class="swt-box">
      <div class="light ">
        <img :src="imgLight" alt="Vue logo" id="swtlight"  style="width: 100px;"><br>
        <p class="NTextSize">Light</p>
        <button @click="lightSwitchOn" class="btn-sp on">ON</button>
        <button @click="lightSwitchOff" class="btn-sp off">OFF</button>
      </div>
      <div class="pump">
        <img :src="imgPump" alt="Vue logo" style="width: 100px;"><br>
        <p class="NTextSize" >Water Pump</p>
        <button @click="PumpSwichOn" class="btn-sp on">ON</button>
        <button @click="PumpSwichOff" class="btn-sp off">OFF</button>
      </div>
    </div>
    
  </div>
  <div class="hello">
      <div class="myfarm-box">
        <div class="mfarm">
          <!-- Link Router -->
          <router-link to="/farm" style="text-decoration: none;color:black;">
            <h1>
              <img alt="farm" src="../assets/sprout_logo.png" style="width: 28px;padding-left: 5px;" />
              My Farm
            </h1>
          </router-link>
          <!-- Date & Time -->
          <div class="myfarm-date tleft">
              <div class="DateAndTime">
                <p>Today : {{displayDate}},2023</p>
                <p>Time : {{currentTime}}</p>
              </div>
              <!-- Planting Date -->
              <ul class="CustomList">
                <li><p style="padding:0;margin:0;font-size: 20px;text-decoration: underline;">Plant Date</p></li>
                <div class="datePlanting">
                  <p class="m-0"> 1 Nov 2022 : First Planting </p>
                    <ul style="padding-left: 22%;margin:0;">
                      <li>- Weed</li><br/>
                      <li>- Basil</li>
                    </ul>
                  <p class="m-0"> 7 Nov 2022 : Second Planting</p>
                </div>
              </ul>
            </div>
        </div>
      </div>
  </div>  
</template>

<script>
export default {
  name: 'HelloWorld',
  
  
  data(){
    return {
      imgLight: require('@/assets/bulb_logo_off.png'),
      imgPump: require('@/assets/water-pump_logo_off.png'),
      Timg: require('@/assets/temperature_logo.png'),
      Himg: require('@/assets/humidity_logo.png'),
      text: '31 °C / °F',
      daysOfWeek: ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'],
      monthsOfYear: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
      currentTime: '',
    };
  },
  mounted(){
    this.getCurrentTime();
  },
  methods: {
    lightSwitchOn(){this.imgLight = require('@/assets/bulb_logo_on.png'),console.log("Light On")},
    lightSwitchOff(){this.imgLight = require('@/assets/bulb_logo_off.png'),console.log("light Off")},
    PumpSwichOn(){this.imgPump = require('@/assets/water-pump_logo_on.png'),console.log("Pump On")},
    PumpSwichOff(){this.imgPump = require('@/assets/water-pump_logo_off.png'),console.log("Pump Off")},
    TextSwitch(){if(this.text === '31 °C / °F'){this.text = '87 °F / °C'}else{this.text = '31 °C / °F'}+console.log("Switch Temp")},
    getCurrentTime(){const now = new Date(); const currentTime = now.toLocaleTimeString(); this.currentTime = currentTime; setTimeout(this.getCurrentTime, 1000);}
  },
  computed: {
    displayDate() {
      const today = new Date();
      const dayOfWeek = this.daysOfWeek[today.getDay()];
      const month = this.monthsOfYear[today.getMonth()];
      const date = today.getDate();

      return `${dayOfWeek} ${date} ${month} `;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  float: left;
  padding-left: 30px;
  width: 400px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.th-box{
  max-width: 100%;
  max-height: 100%;
}
.th-box .temp{
  display: inline-block;
  padding: 10px 25px;
  color: #ebdcdc;
  font-size: 32px;
  font-weight: 100;
  height: 225px;
  width: 400px;
  text-shadow: 3px 2px rgba(0, 0, 0, 0.25);
  background-color: #da4949;
  border-radius: 16px;
  margin: 30px 0px;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);

}
.th-box .humn{
  display: inline-block;
  padding: 10px 25px;
  color: #ebdcdc;
  font-size: 32px;
  font-weight:  100;
  height: 225px;
  width: 400px;
  text-shadow: 3px 2px rgba(0, 0, 0, 0.25);
  background-color: #4994da;
  border-radius: 16px;
  margin: 0px 0px;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.swt-box {
  padding-left: 12%;
  max-height: 100%;
  max-width: 100%;
}
.swt-box .light{
  display: inline-block;
  padding: 10px 100px;
  color: #0b0b0b;
  font-weight: 900;
  border-radius: 16px;
  height: 225px;
  width: 200px;
  background-color: #fa9f9f;
  margin: 30px 0px;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.swt-box .pump{
  display: inline-block;
  padding: 10px 100px;
  color: #0b0b0b;
  font-weight: 100;
  height: 225px;
  width: 200px;
  background-color: #fa9f9f;
  margin: 0px 0px;
  border-radius: 16px;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.btn-sp{
  padding: 6px;
  margin-left: 10px;
  width: 80px;
  color: black;
  cursor: pointer;
  background-color: white;
}
 .on{
  border-color: #04AA6D;
  color: #04AA6D;
  font-size: 16px;
  font-weight: bold;
}
.on:hover{
  background-color: #04AA6D;
  color: white;
}
.off{
  border-color: #f44336;
  color: #f44336;
  font-size: 16px;
  font-weight: bold;

}
.off:hover{
  background-color: #f44336;
  color: white;
}
.myfarm-box{
  max-width: 100%;
  max-height: 100%;
  padding-left: 12%;
}
.myfarm-box .mfarm{
  display: inline-block;
  padding: 10px 100px;
  color: #0b0b0b;
  font-weight: 900;
  border-radius: 16px;
  height: 500px;
  width: 100%;
  background-color: #a8fa9f;
  margin: 30px 0px;

  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.TextSize{
  font-size: 40px;
  font-weight: bold;
}
.hoverText:hover{
  color: #4994da;
  cursor: context-menu;
}
.NTextSize{
  font-size: 20px;
  font-weight: bold;
}
.tleft{
  text-align: left;
}
.m-0{
  margin:0;
}
</style>
