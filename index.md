# Krishna Garg

I am a sixteen year old Junior attending Kennett High School in North Conway. My main focus is Computer Science in which I am proficient having completed many projects along side teammates and independently. I am skilled at using coding languages 'C' and 'javaScript'. I also have a working understanding of HTML and CSS and am proficient in reactNative. 

## My Projects 
### The Tax Calculator Project

### Brief Description
While working in CS50 I was able to gather enough knowledge about the coding language 'C' that I began to work on my own projects. So I decided to work on one big project to end the year.
I decided to work with 'C' in order to make a tax calculator. I had never really understood how taxes worked so this seemed like a great opportunity to extend my knowledge and apply coding
to a real life issue. This tax calculator uses arrays, if else statements, and lists in order to calculate a persons tax amount based on their social status and income. 

### How it Works
Basically the code gathers inputs such as income and what tax bracket the person would fall under then based on those inputs runs the income through certain if statements that multiply the income by percentages. 

### Problems Encountered During Project
One of the problems I encountered during the making of this project was the size and length of the code. The code below is the condesed version of the original code. Originally the code for this calculator was extremley long and would have been extremley difficult to manage. But with the help of some friends and my teacher I was able to create an algorithm that both made the code easier to mange and easier to read. I was able to make this algorithm using arrays and lists, saving them as variables, and then running the variables through functions I designed myself. 



### The Code 
```
// Author: Krishna Garg
// Project: AP Create task
// Tax and income calculator
#include <stdio.h>
#include <cs50.h>
#include <math.h>
/*
To understand which tax bracket they are in I must first get which category the person falls under
1. Single
2. Married filling jointly
3. Married filling seperatley
4. Head of Household
(possibilty to use switch statement)
Then based on this information and the information on https://www.nerdwallet.com/blog/taxes/federal-income-tax-brackets/
Then I must find out how much money they make a year. With this information I will be able to use if statements to get the amount of
money they pay in tax after everytime they make a certain amount of money
At the end I will return how much money they pay in taxes and how much money they are left with
One way to expand on this project is to request all the expenses they pay on a monthly basis not including food and gas becuase they are
not constant variables and take all of those varables and subtract that from the remaining balance of money after taxes. This will give
how much money they are left to spend after all of the expenses they have.

Ask user for social status category
Ask user for total income
make duplicate income called gross_income which you can use to print the amount of money user has after taxes

Calculate taxes
Display taxes paid / net income

Abstraction:



Budget Calculator?
*/
long calculateTaxes(int taxBracket[], long income);
enum bracket{ bracket1, bracket2, bracket3, bracket4, bracket5, bracket6, bracket7};

int main (void)
{
    long income;

    do
    {
        income = get_long("How much money do you make in one year:");
    }
    while(income <= 0);

    long gross_income = income;

    int social_status;
    do
    {
        social_status = get_int("Are you: 1. Single\n"
                                          "2. Married filling jointly\n"
                                          "3. Married filling seperatley\n"
                                          "4. Head of Household\n"
                                          "Enter: 1, 2, 3, 4:");
    }
    while(social_status > 4 || social_status < 1);
    long taxes = 0;

    int singleBracket[] = {9700, 39457, 84200, 160725, 204100, 510300};
    int marriedJointlyBracket[] = {19400, 78950, 168400, 321450, 408200, 612350};
    int marriedSeperateBracket[]= {9700, 39457, 84200, 160725, 204100, 306175};
    int HeadofHouseholdBracket[]= {13850, 52850, 84200, 160700, 204100, 510300};


    // Start if Statments
    if(social_status == 1)
    {
        taxes = calculateTaxes(singleBracket, income);
    }
    if(social_status == 2)
    {
        taxes = calculateTaxes(marriedJointlyBracket, income);
    }
    if(social_status == 3)
    {
        taxes = calculateTaxes(marriedSeperateBracket, income);
    }
    if(social_status == 4)
    {
        taxes = calculateTaxes(HeadofHouseholdBracket, income);
    }

    printf("Your taxes are: $%li\n", taxes);
    printf("Left Over Money:$%li\n", gross_income - taxes);


   //marriedJointlyBracket[]
   /*
    if (income > taxBracket[bracket6])
        {
            taxes += (income - taxBracket[bracket6]) * .37;
            income = income - taxBracket[bracket6];
        }
        else if (income > taxBracket[bracket5] && income <= taxBracket[bracket6])
        {
            taxes += (income - taxBracket[bracket5]) * .35;
            income = income - taxBracket[bracket5];
        }
        else if (income > taxBracket[bracket4] && income <= taxBracket[bracket5])
        {
            taxes += (income - taxBracket[bracket4]) * .32;
            income = income - taxBracket[bracket4];
        }
        else if (income > taxBracket[bracket3] && income <= taxBracket[bracket4])
        {
            taxes += (income - taxBracket[bracket3]) * .24;
            income = income - taxBracket[bracket3];
        }
        else if (income > taxBracket[bracket2] && income <= taxBracket[bracket3])
        {
            taxes += (income - taxBracket[bracket2]) * .22;
            income = income - taxBracket[bracket2];
        }
        else if (income > taxBracket[bracket1] && income <= taxBracket[bracket2])
        {
            taxes += (income - taxBracket[bracket1]) * .12;
            income = income - taxBracket[bracket1];
        }
        else if(income <= taxBracket[bracket1])
        {
            taxes += (income) * .1;
            income = 0;
        }



    printf("Your Income: %li, How Much You Pay in Taxes: %li", gross_income - taxes, taxes);
        */

}


long calculateTaxes(int taxBracket[], long income)
{
    long taxes = 0;

    if (income > taxBracket[bracket6])
    {
        taxes += (income - taxBracket[bracket6]) * .37;
        income = income - taxBracket[bracket6];
    }
    if (income > taxBracket[bracket5] && income <= taxBracket[bracket6])
    {
        taxes += (income - taxBracket[bracket5]) * .35;
        income = income - taxBracket[bracket5];
    }
    if (income > taxBracket[bracket4] && income <= taxBracket[bracket5])
    {
        taxes += (income - taxBracket[bracket4]) * .32;
        income = income - taxBracket[bracket4];
    }
    if (income > taxBracket[bracket3] && income <= taxBracket[bracket4])
    {
        taxes += (income - taxBracket[bracket3]) * .24;
        income = income - taxBracket[bracket3];
    }
    if (income > taxBracket[bracket2] && income <= taxBracket[bracket3])
    {
        taxes += (income - taxBracket[bracket2]) * .22;
        income = income - taxBracket[bracket2];
    }
    if (income > taxBracket[bracket1] && income <= taxBracket[bracket2])
    {
        taxes += (income - taxBracket[bracket1]) * .12;
        income = income - taxBracket[bracket1];
    }
    if(income <= taxBracket[bracket1])
    {
        taxes += (income) * .1;
        income = 0;
    }

    return taxes;
}
```

## A Themed Arcade Website
### Brief Description
Using Django, our team was able to build a responsive themed spirit week website. Inside of this website was a fully functional arcade with 4 classic games that were coded by individuals in the group. This project was created for the spirit week of the school I was attending. Because it was for the school the website had login usernames and passwords for all of the students who used it. We set up a database that could hold all of this information. The population of the group was slit up into four seperate teams the handled each aspect of the code.

### Problems Encountered
Some of the problems encountered while creating this project were making a leaderboard, updating a leaderboard, saving login information, and checking login information. I was apart of the functionality team that dealt with these kinds of problems. Fortunatley Django had a swear checker that we implemented while fixing the checking login problem. Django also had a saving log in information function in their library. So the only problem left was setting up and updating the leaderboard automatically. This was solved by extensive research and some magic done in Python by some exceptional individuals in the group. 

### The Project Result
Please feel free to check out the final result of the website.
Link:

## Virtual Air Hockey
### Brief Description
Virtual Air Hockey was an add on to the themed website. It was one of the arcade games that went into the over all project. To create this project my partner and I used p5 which is an extension of javascript which is made for more artistic and game like code. But even p5 does not have the necessary logic and physics needed to create a game like virtual air hockey. To incorporate the necessary logic and physics into the code my partner and I found a p5.play library which allowed us to use physics concepts like velocity into our code, in turn making it seem more and more like actual air hockey. This game kept score and increased velocity with every hit. It is a one player game in which the user faces off against an ai.

### Problems Encountered
During the game making process there was an issue that the game started as soon as the page opened up. To fix this we incorporated states into our code which made it so that the user would have to click in order to start any motion in the game. Adding states was difficult to do once we had finished the code since we had to go back and modify the whole code to allow states to take action. 

### The Code
```
//Sprites and background variables (keep all)
var spr,
    ai,
    puck;
var paddles;
var computerPos;
var scoreText;
var counter;
var finalscore;
var button;

const canvasDimensions = [600, 400];
const RAD2DEG = 180 / Math.PI;
const DEG2RAD = Math.PI / 180;
state = 1;

function rand(a, b) {
    return (a + Math.random() * (b - a));
}

function setup() {
    createCanvas(canvasDimensions[0], canvasDimensions[1]);
    background(20);

    fill(255);
    textAlign(CENTER);

    paddles = new Group();

    spr = createSprite(20, height / 2, 5, 50);
    spr.shapeColor = 'white';
    paddles.add(spr);

    ai = createSprite(width - 20, height / 2, 5, 50);
    ai.shapeColor = 'white';
    paddles.add(ai);

    puck = createSprite(width / 2, height / 2, 8, 8);
    puck.shapeColor = '#c6ed2c';

    aiPos = Array.apply(null, Array(10)).map(Number.prototype.valueOf, height / 2);
    score = [0,0];

    puck.setSpeed(10, rand(-15, 15));
}

function draw() {
    background(20);
    drawSprites();

    // set play paddle position to mouse position, within bounds
    spr.position.y = Math.max(0, Math.min(height, mouseY));

    // perfect computer player
    // computer.position.y = ball.position.y;

    // delayed computer player
    aiPos.push(puck.position.y);
    ai.position.y = aiPos.shift();

    // wall collisions
    if (puck.position.y < 4 || puck.position.y > height - 4) {
        puck.velocity.y *= -1;
    }

    // goal collisions
    if (puck.position.x < 4) {
        score[1]++;
        puck.position.x = width/2;
        puck.position.y = height/2;
        puck.setSpeed(10, rand(170,190));
    }
    else if (puck.position.x > width - 4) {
        score[0]++;
        puck.position.x = width/2;
        puck.position.y = height/2;
        puck.setSpeed(10, rand(-15,15))
    }

    // ball/paddle collisions
    puck.overlap(paddles, function(ball, paddle) {
        puck.velocity.x *= -1.01;
        puck.velocity.y += (puck.position.y - paddle.position.y) / 20;
    });

    scoreText = score[0] + " – " + score[1];
    text(scoreText, width/2, 20);
  
    
  
  
    
  
  if (score[0] == 8){
    puck.setSpeed(0, rand(-15,15))
    scoreText = "Player 1 is the winner";
    text(scoreText, width/2, 40);
    }
         
  else if (score[1] == 8){
    puck.setSpeed(0, rand(-15,15));
    scoreText = "AI is the winner";
    text(scoreText, width/2, 40);
    }
  

  finalscore = 0;
  finalscoreText ="Your Ultimate Score is " + finalscore;
  if(score[0] == 8){
    finalscore = finalscore + 25;
    text(finalscoreText, width/2, 60);
  }
  else if(score[1] == 8){
    finalscore = finalscore;
    text(finalscoreText, width/2, 60);
  }
  
    
  
  

  
  
}
```

### Contact Me
1. Email: [kgarg1675@gmail.com]
2. Phone: 603-377-2566
3. Github:[kgkhs001]



