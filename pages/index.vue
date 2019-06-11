<template>
  <section class="container">
    <div :style="{ 'background-color': '#' + color_1, fontSize: '10' + 'px' }"><span><p>{{color_1}}</p></span></div>
    <div :style="{ 'background-color': '#' + color_2, fontSize: '10' + 'px' }"><span><p>{{color_2}}</p></span></div>
    <div :style="{ 'background-color': '#' + color_3, fontSize: '10' + 'px' }"><span><p>{{color_3}}</p></span></div>
    <div :style="{ 'background-color': '#' + color_4, fontSize: '10' + 'px' }"><span><p>{{color_4}}</p></span></div>
    <div :style="{ 'background-color': '#' + color_5, fontSize: '10' + 'px' }"><span><p>{{color_5}}</p></span></div>
  </section>
</template>

<script>

export default {
  data () {
    return {
      hex_values: ['0','1','2','3','4','5','6','7','8','9','a','b','c','d','e','f'],
      color_1: '',
      color_2: '',
      color_3: '',
      color_4: '',
      color_5: ''
    }
  },
  methods: {
    generate_color: function() {
      var color = ""

      for (let i=0; i < 6; i++) {
        color += this.hex_values[Math.floor(Math.random()*this.hex_values.length)]
      }
      return color;
    },
    set_colors: function() {
      console.log('hello')
      

      
    }
  },
  created() {
    this.color_1 = this.generate_color();
    this.color_2 = this.generate_color();
    this.color_3 = this.generate_color();
    this.color_4 = this.generate_color();
    this.color_5 = this.generate_color();
  },
  mounted() {
    var self = this
    window.addEventListener('keydown', function(e) {
      console.log(e.keyCode);
      if (e.keyCode == 32) { 
        self.color_1 = self.generate_color();
        self.color_2 = self.generate_color();
        self.color_3 = self.generate_color();
        self.color_4 = self.generate_color();
        self.color_5 = self.generate_color();
      }
    });
  }



}
</script>

<style>
.container {
  display: flex;
  flex-direction: row;
}

div {
  flex-grow: 1;
  height: 100vh;
}

div span {
  padding: 10px;
  display: block;
  background-color: rgba(0, 0, 0, .1);
}

div p {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #ffffff;
  font-size: 30px;
  font-weight: 300;
}

div p::before { 
  content: "#";
}
</style>
