# Random On/Off

## Introduction @unplugged 

Let's turn pixles on and off with the A and B buttons - RANDOMLY!

![One Light on and off](https://raw.githubusercontent.com/rypsmith/randomonoff/master/randomonoff.gif)

## Step 1: Getting Set-up

Start out by removing the forever and the ``||basic:forever||`` and the ``||basic:on start||`` blocks and bring in two ``||input:on button "A" pressed||`` blocks. Change one block to ``||input:on button "B" pressed||``.

## Step 2: What is a variable

Variables can be thought of as containers that information can be put into and stored. Go the ``||variables:Variables||`` category and make two variables. Give them two different names like random1 and random2.

## Step 3: Place the variables

Take the variables that you have made and put them into the ``||input:on button "A" pressed||`` block. 

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = 0
    random2 = 0
})
input.onButtonPressed(Button.B, function () {
	
})
```

## Step 4: Store the Random Numbers

The two variables will keep and store the random number that will be picked. This will let you turn on and off the same LED pixel - even though the pixel is randomly picked. Put a ``||math:pick random||`` into both ``||variables:set ... to||`` blocks.

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = randint(0, 10)
    random2 = randint(0, 10)
})
input.onButtonPressed(Button.B, function () {
	
})
```

## Step 5: Make adjustments

Adjust the range of of the random numbers, remember that there are five pixels and they are represented by the numbers 0 to 4.

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = randint(0, 4)
    random2 = randint(0, 4)
})
input.onButtonPressed(Button.B, function () {
	
})
```

## Step 6: Get ready to use variables

Go and grab a ``||Led:Plot||`` block and place it under the two ``||variables:set ... to||`` blocks.

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = randint(0, 4)
    random2 = randint(0, 4)
    led.plot(0, 0)
})
input.onButtonPressed(Button.B, function () {
	
})
```

## Step 7: Use the variables

Go into the ``||variables:Variables||`` category and look for the two custom variable block that you made.

![New Variable Blocks](https://raw.githubusercontent.com/rypsmith/randomonoff/master/variableblocks.png)

Take one and put it into the x value for the ``||Led:plot||`` block and place the other into the y value. 

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = randint(0, 4)
    random2 = randint(0, 4)
    led.plot(random1, random2)
})
input.onButtonPressed(Button.B, function () {
	
})
```

# Step 8: Get ready to turn off the lights.

Now you need to turn the same LED off. Put a ``||Led:unplot||`` block inside the ``||input:on button "B" pressed||`` block.

```blocks
let random1 = 0
let random2 = 0
input.onButtonPressed(Button.A, function () {
    random1 = randint(0, 4)
    random2 = randint(0, 4)
    led.plot(random1, random2)
})
input.onButtonPressed(Button.B, function () {
    led.unplot(0, 0)
})
```