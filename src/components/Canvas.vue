<template>
  <div id="canvas"></div>
</template>

<script>
import P5 from 'p5' // Package from npm

export default {
  name: 'App',
  mounted() {
    const script = p5 => {
      let x = 760;
      let y = 350;
      let easing = 0.1;
      // These are your typical setup() and draw() methods
      p5.setup = () => {
        p5.createCanvas(1520, 700);
        p5.noStroke();
      };
      p5.draw = () => {
        //p5.clear();
        //p5.ellipse(p5.mouseX, p5.mouseY, 80, 80);
        p5.background('powderblue');

        let targetX = p5.mouseX;
        let dx = targetX - x;
        x += dx * easing;

        let targetY = p5.mouseY;
        let dy = targetY - y;
        y += dy * easing;

        
        p5.ellipse(x, y, 100, 100);
        
      }; 
    }
    // Attach the canvas to the div
    const p5canvas = new P5(script, 'canvas');
  },
  
}
</script>

<style></style>