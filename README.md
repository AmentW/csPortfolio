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
    > Starfield took a great leap forward by using some polymorphic tools to simulate a beautiful night sky. This lab was by far the most involved out of them all. It used a Particle interface that implemented all the same methods to each class. Every class used the same methods, but had differences in how they performed them. For instance the NormalParticle class used some triginometry functions from the Math class to animate the Paritcles' elliptical movement. I think a source of pride for me in this project was calculating the different particles' movements. I experimented a lot with changing values in the calculations and seeing how the particles would react. I further manipulated their movements by adding if statements that acted as boundaries for how far the particle can move. 

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

### Here are the responses to the Portfolio Reflection
- **Identify the most significant hurdle you encountered last trimester. Write about what it was and how it was resolved.**
    > The most significant hurdle I faced was working on the Starfield project. I haven't worked with interfaces in the past and in the first few iterations of my code I could tell I wasn't using them properly. I asked my peers about interfaces, but they didn't know very much about them either. To find the answer to my questions I read information about interfaces on Stackoverflow and the Java api. It took me a while to understand that an interface is used when you have many classes with similar traits, but minor differences. I now undertsand how powerful interfaces can be and will look for more opportunities to include them in my code. 

***

- **Describe the incremental and iterative development process of your included code, focusing on two distinct points in the development process.**
    > In the Starfield project I spent a large ammount of time tinkering with different PI values. By changing the divisor of the pie value, I can create a wider range of cirlular paths. 
    ```
    for ( int i = 0; i< p.length; i++) {
    p[i] = new NormalParticle(pie);
    pie += Math.PI/24;
  }
    ```
    My earlier editions had a lot more objects being created and drawn. To make sure the particles don't overlap I can change that divisor, but when you get to about 1000-10000 objects being drawn, the difference in PI values isn't large enough to make a difference.
    
    > Another significant section of my code from Starfield is an if-statement that changes the color of the particles after a given time interval. I created this if-statement so change the color of each ball to become a random new value after 100 loops of the show() method. 
    ```
    if (test == 0) {
      randC();
      test = 100;
    }
    test --;
    ```
    > I initally tried using the timer and delay methods in Processing but I couldn't figure out how to make it work the way I want it to. This little if statement is what makes my Starfield lab look so pretty. If I hadn't used the if-statement, my particles would be constantly changing color, making it impossible to even see the things. 
    > I created Starfield mostly independetly, the only times it was collaborative were when I became stuck and needed some help. I got assistance from both my peers and the internet. I consulted the internet whenever I needed a quick answer to something I knew was an easy fix. I also got help from my peers, however, the advice I got from them often wasn't the answer to my problem. I can only expect this as my peers are also coming up with the same problems. What I did find constructive was the ideas my peers had inspired me to make unique tweaks to my program, like the NormalParticles orbit. 

***
