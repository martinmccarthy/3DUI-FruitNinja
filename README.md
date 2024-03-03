# Fruit Ninja 3DUI Proj2 ReadMe

### What I contributed
- I developed this project by myself, everything in the video has been created and implemented by me.
- Created 5 Types of Fruits:
  - Lemon is a normal fruit that spawns smaller fruits to throw at the user
  - Strawberry implements the fruit throwing logic along with teleportation
  - Orange implements fruit throwing logic with a jumping effect that also creates a shockwave dealing damage to the user if they are within the range of it.
  - Kiwi has fruit throwing logic, but randomly throws bombs at the user which will instantly end the game if they hit them. Kiwi also has a forcefield that can only be destroyed if the player uses parry on a bomb to return it to the fruit.
  - Blueberry has fruit throwing logic and also can spawn other enemy fruits.
- Movement interactions for the following:
  - Hands behind back allows user to move forward as if they are running like a ninja, the user can also use joysick for movement if inaccessible or more precise movement is needed.
  - Hands above head allows the user to fly in the direction they're facing.
  - Flicking controllers upwards triggers jump (Velocity tracking)
- Three weapons implemented
  - A button cycles the weapons.
  - Sword has slicing and parrying, holding button while the sword is horizontal will allow parrying.
  - Grapple gun is activated by left trigger, bringing food towards the user.
  - Ninja star is activated by left trigger, shooting towards the nearest fruit the user is looking at.
- Voice detection
  - Wit.ai from Meta with the Meta Voice SDK, listens to the user's microphone when they press the Y button. Sends an API call when the user finishes speaking and does analysis on what they say, triggers controller in the game if the analysis returns a high confidence level.


### What Works
The application works very well, the requirements are all met, however, I wish I would've been able to add more attacks to the sword, ideally different attacks for different fruits or maybe environment interactions with slicing like bamboo blocking the path. The fruits all can attack the user, draining the player's energy when they hit them with their fruits, and can be destroyed when the user gets close enough to slice them or if they are within range of a ninja star through. The voice detection feature works, but I wish it would respond a little faster. The grappling hook works well, and can grapple both food and fruit, for the purposes of demonstration I didn't display grappling the fruits since it doesn't add any utility to the game. The flying and jumping work well and user movement feels like it would be how a ninja moves. The character controller tracks with the position of the headset, which allows the user to crouch.

### What Doesn't Work
The movement works, however flying can make you feel motion sick due to the high speed and effect of gravity from a high height and isn't the best way to go about it.

### Bugs
- The sound effect for swinging the sword was glitchy because the movement was too sensitive so I had to remove it
- GUI for telling the user there is voice activation wouldn't reset once the values were sent to the API so I removed it as well.
- The threshold for jumping isn't always registered, and won't trigger the jump until after the user triggers another movement, the jump itself will still work but won't trigger until there is another move.

### Problems Encountered
- I originally had faces on the fruits, but the collider on the face would always cause throwing the fruit to hit it once I made contact with it.
- Integrating the AI for voice detection was challenging, at first I was not picking up the mic from the Quest which made it hard to tell if it was an API problem or not. It also took me quite some time to figure out how to send up the API call from the user interaction to call it.
- Flying took a long time to integrate with my player controller, I wanted something that would give the user controller over the flight but also prevent them from flying too far into the sky. This took a lot of time to fine tune and also to try to work with preventing motion sickness, ultimately it still doesn't feel all that good but it did end up working.
