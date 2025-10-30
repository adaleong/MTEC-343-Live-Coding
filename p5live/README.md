We kept having an issue where the visuals on screen weren't syncing. We started with premade sketches and learned a bit more about how Hydra worked in the context of p5. I also kept trying to add an image of my cat which wasn't working.

Anything we did wrong would make the screens black out which was frustrating.

```

/*
	_HY5_hydra_p5_hydra // cc teddavis.org 2024
	pass p5 into hydra
	docs: https://github.com/ffd8/hy5
*/

let libs = ['https://unpkg.com/hydra-synth', 'includes/libs/hydra-synth.js', 'https://cdn.jsdelivr.net/gh/ffd8/hy5@main/hy5.js', 'includes/libs/hy5.js']

// sandbox - start
s0.initP5()
P5.toggle(0)
H.toggle(0)

noize().out()

var H2 = HY5.hydra('hydra2', 'synth') // 2nd hydra
synth.s0.initP5()
H2.z(2) // double check on top

H2.pixelDensity(2) // 2x = retina, set <= 1 if laggy

synth.src(synth.s0)
	.modulateScale(synth.src(synth.o0).scale(100), 1)
	 .repeatX(10)
	 .repeatY (10)
	 .saturate()
	 .saturate()
	.out()
	osc(6, 0, 0.8)
  .color(1.14, 0.6,.80)
  .rotate(0.92, 0.3)
  .pixelate(20, 10)
  .blend(osc(40, 0.03).thresh(0.4).rotate(0, -0.02))
  .modulateRotate(osc(20, 0).thresh(0.3, 0.6), () => 0.1 + mouse.x * 0.002)
  
  .out(o0)
  voronoi(10,-0.1,5)
.add(osc(1,0,1)).kaleid(11)
.scale(1,1,2).colorama(100).out(o1)
src(o1).mult(src(s0).modulateRotate(o1,100), -0.5)
  .out(o0)
  
// sandbox - end


function setup() {
	createCanvas(windowWidth, windowHeight, WEBGL)
	noStroke()
}

function draw() {
	clear()
	rotateY(frameCount/4)
	rotateX(frameCount/4)
	orbitControl(3)
	
	texture(H.get())
	sphere(height/2)
}

function keyPressed(){
	if(key == 'S'){
		H2.save() // save 2nd hydra
	}
	
	
}

osc(50).rotate( () => time%360 ).out(o0)
osc(100,-0.0018,0.17).diff(osc(20,0.00008).rotate(Math.PI/0.00003))
.modulateScale(noise(1.5,0.18).modulateScale(osc(13).rotate(()=>Math.sin(time/22))),3)
.color(11,0.5,0.4, 0.9, 0.2, 0.011, 5, 22,  0.5, -1).contrast(1.4)
.add(src(o0).modulate(o0,.04),.6, .9)
  //.pixelate(0.4, 0.2, 0.1)
.invert().brightness(0.0003, 2).contrast( 0.5, 2, 0.1, 2).color(4, -2, 0.1)
.modulateScale(osc(2),-0.2, 2, 1, 0.3)
 .posterize(200) .rotate(1, 0.2, 0.01, 0.001)
 .color(22, -2, 0.5, 0.5, 0.0001,  0.1, 0.2, 8).contrast(0.18, 0.3, 0.1, 0.2, 0.03, 1) . brightness(0.0001, -1, 10)
	.out()
	
```