## Krishna Garg

I am a sixteen year old Junior attending Kennett High School in North Conway. My main focus is Computer Science in which I am proficient having completed many projects along side teammates and independently. I am skilled at using coding languages 'C' and 'javaScript'. I also have a working understanding of HTML and CSS and am proficient in reactNative. 

### My Projects 
### The Tax Calculator Project

## Brief Description
While working in CS50 I was able to gather enough knowledge about the coding language 'C' that I began to work on my own projects. So I decided to work on one big project to end the year.
I decided to work with 'C' in order to make a tax calculator. I had never really understood how taxes worked so this seemed like a great opportunity to extend my knowledge and apply coding
to a real life issue. This tax calculator uses arrays, if else statements, and lists in order to calculate a persons tax amount based on their social status and income. 

## Problems Encountered During Project
One of the problems I encountered during the making of this project was the size and length of the code. The code below is the condesed version of the original code. Originally the code for this calculator was extremley long and would have been extremley difficult to manage. But with the help of some friends and my teacher I was able to create an algorithm that both made the code easier to mange and easier to read. I was able to make this algorithm using arrays and lists, saving them as variables, and then running the variables through functions I designed myself. 



## The Code 
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

2. A Themed Arcade Website
3. Virtual Air Hockey


### Contact Me
1. Email: [kgarg1675@gmail.com]
2. Phone: 603-377-2566
3. Github:[kgkhs001]



