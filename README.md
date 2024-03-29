# twittercontrol
* Twittercontrol allows people to use twitter to control applications in python
* In the demonstration, you will tweet a question and then it will reply with a response on your screen
* It works by each keyword has a corresponding action (function) completed when a keyword is found within a tweet that mentions your twitter handle


## Setup and Test twittercontrol

1 - Install twython (https://github.com/ryanmcgrath/twython) with ```pip install twython```

2 - Go to https://projects.raspberrypi.org/en/projects/getting-started-with-the-twitter-api/3 and follow the instructions to create a twitter developer account

3 - Go to https://projects.raspberrypi.org/en/projects/getting-started-with-the-twitter-api/4 and follow the instructions to create a developer account - Make sure you can access the consumer, consumer secret, access token and access token secret keys!

4 - Download this GitHub repository into a folder on your computer

5 - Go into *twittercontrol.py* and copy and paste the consumer, consumer secret, access token and access token secret keys - don't forget to put in the twitter handle you want to check to see if someone has posted!

```python
twitterHandle='<your twitter handle>'
consumer_key = "<consumer api key>"
consumer_secret = "<consumer api secret key>"
access_token = "<access token key>"
access_token_secret = "<access token secret>"
```

6 - Then run *twittercontrol.py* and tweet from your account *@your_twitter_handle What is your favourite single-board computer?*
  
7 - The script should then print **Raspberry Pi 4** if it has worked

## Create your own action

1 - Open the *actions.py* script in your editor

2- Create a new function below this code (but before the *keywords* and *actions* lists):
```python
#what is your favourite single-board computer
def what_is_your_favourite_sbc():
    print('Raspberry Pi 4!')
```
3- Within the function, type the code that you want to be completed once the keyword has been found

4- In the list *keywords* add the words that you want to be typed after your twitter handle

5- In the list *actions* add the name of your function but do not put the brackets after it!

6- Then tweet *@your_twitter_handle keyword* and hopefully your actions should be completed

Below is an example of what you could do to control a robot on a Raspberry Pi using gpiozero(https://gpiozero.readthedocs.io/en/stable/index.html):
```python
from gpiozero import Robot
robot = Robot(left=(4, 14), right=(17, 18))

#what is your favourite single-board computer
def what_is_your_favourite_sbc():
    print('Raspberry Pi 4!')
#move robot forward
def move_robot_forward():
    robot.forward()
   
keywords=['What is your favourite single-board computer?','move robot forward']
actions=[what_is_your_favourite_sbc,move_robot_forward]
```

Please tell me if there are any problems with the code!


