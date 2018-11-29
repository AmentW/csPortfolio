# Welcome to my Computer Science Portfolio
---

### Here are some of my webistes I made using HTML and CSS


* **WebPage1** [here](https://amentw.github.io/testWeb/dogPage/) *Source Code* [there](https://github.com/AmentW/testWeb/)
  * This webpage is called dogPage. It was my first crack at website coding, so it doesn't have very much HTML.
* **WebPage2** [here](https://amentw.github.io/testWeb/pagePage) *Source Code* [there](https://github.com/AmentW/testWeb/)
  * This webpage is called pagePage. I created a new webpage idea and added even more HTML.
* **WebPage3** [here](https://amentw.github.io/testWeb/finalPage) *Source Code* [there](https://github.com/AmentW/testWeb/)
  * This webpage is called finalPage. I made improvements to pagePage by adding some CSS styling to it.
> While tinkering with the HTML and CSS I soon learned how tedious the formatting can become. None the less I recognize it's utility in web design with Javascript. I think a source of pride in this project was my CSS styling. In my project I used some CSS to edit my text and background with colors. I also used it to link different sections of my website.

***

### Here are some of the projects I made in Java using Processing
* **Lightning** [here](https://amentw.github.io/lightning2/Lightning/) *Source Code* [there](https://github.com/AmentW/lightning2)
> Lightning was a project that familiarized me with how animation works in Processing. The draw method used some basic x and y coordinates to write new line segments. I also used some if statements to create an invisible box that the lightning will show in. A source of pride in this project was undertsanding how the draw() method works. I learned that I have to pay close attention to when I draw the line so that it isn't layered behind the black background.

***
* **Dice** [here](https://amentw.github.io/dice3/Dice) *Source Code* [there](https://github.com/AmentW/lightning2)
> Dice didn't bring anything new the to table, but it did require some more planning. This lab had some opportunity to simplify code down to only far fewer lines within the show() method. This lab was pretty easy to complete once I figured out how each die needed to be drawn as. A source of pride for me in this project is my randC() method I wrote. It picks a random color within a range that creates a pastel-like color. It also has additional variables (r1, g1, and b1) that are a brighter, neon color. This color changer is called elsewhere in my code to change the color of every dice, and set of die holes. I used this method in my other programs too.

>This is the randC() method:
```
void randC() {
    r = (int)((Math.random() * (255-155) +155));
    g = (int)((Math.random() * (255-155) +155));
    b = (int)((Math.random() * (255-155) +155));

    r1 = (int)((Math.random() * (155-50) +50));
    g1 = (int)((Math.random() * (155-50) +50));
    b1 = (int)((Math.random() * (155-50) +50));
  }
```
***
* **Chemotaxis** [here](https://amentw.github.io/chemotaxis4/) *Source Code* [there](https://github.com/AmentW/chemotaxis4)
> Chemotaxis used objects to create lots of circles that could make different movements independently of eachother. The lab wanted us to use math.random() and incrememnt the x and y positions of each ball. Instead I used a new data type called PVectors. I think this was a source of pride in my code because I went out and learned some new content not being taught in class. I spend several hours reading through the Processing api and tutorial on PVectors. I took notes and actually studied the material, something I don't normally do. I now see different opportunities in my code where using a PVector would work better. I think I've developed a proper understanding of the PVector class. 

>This is some code using PVectors:
```
  Ball (int x, int y) {
    this.x = x;
    this.y = y;
    location = new PVector(this.x, this.y);
    velocity = new PVector(((int)(Math.random() * (4)) +1), ((int)(Math.random() * (4)) +1));
    acceleration = new PVector(this.x/500, this.y/500);
  }
  void randC() {
    r = ((int)(Math.random() * (155) + 100));
    g = ((int)(Math.random() * (155) + 100));
    b = ((int)(Math.random() * (155) + 100));
  }
  void move() {
    location.add(velocity);
    velocity.add(acceleration);
  }
  void show() {
    if (location.x > 535 || location.x < 65) {
      velocity.x *= -1;
      randC();
      fill(r, g, b);
    }
    if (location.y >735 || location.y < 65) {
      velocity.y *= -1;
      randC();
      fill(r, g, b);
    }
    ellipse(location.x, location.y, 15, 15);
  }
}
```
***
* **Starfield** [here](https://amentw.github.io/starfield5/starfield) *Source Code* [there](https://github.com/AmentW/starfield5)
> Starfield took a great leap forward by using some polymorphic tools to simulate a beautiful night sky. This lab was by far the most involved out of them all. It used a Particle interface that implemented all the same methods to each class. Every class used the same methods, but had differences in how they performed them. For instance the NormalParticle class used some triginometry functions from the Math class to animate the Paritcles' elliptical movement. I think a source of pride for me in this project was calculating the different Particles' movements. I experimented a lot with changing values in the calculations and seeing how the Particles would react. I further manipulated their movements by adding if statements that acted as boundaries for how far the particle can move. 

> Here is the NormalParticle class. Notice the boundaries and how they permanently change the particles' orbit.
```
interface Particle {
  void move();
  void show();
  void randC();
}
class NormalParticle implements Particle {
  double x, y, angle, speed;
  int r, g, b;
  int test = 0;
  int timer = 0;
  NormalParticle(double pie) {
    x = width/2;
    y = height/2;
    angle = pie;
    speed = 10;
  }
  void move() {
    x += Math.cos(angle) * speed;
    y += Math.sin(angle) * speed;
    angle += .047;
    // X boundaries
    if ( x > 830) {
      x = 830;
    } else if (x < 170) {
      x = 170;
    }
    // Y boundaries
    if ( y > 830) {
      y = 830;
    } else if (y < 170) {
      y = 170;
    }
  }
  // color change
  void randC() {
    r = ((int)(Math.random() * (155) + 100));
    g = ((int)(Math.random() * (155) + 100));
    b = ((int)(Math.random() * (155) + 100));
  }
  void show() {
    noStroke();
    if (test == 0) {
      randC();
      test = 100;
    }
    test --;
    fill(r, g, b);
    ellipse((int)x, (int)y, 20, 20);
  }
}
```
***

### Here are the answers to the Portfolio Reflection
