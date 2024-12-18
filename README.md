This is a small modification of the K3NG keyer as defined for the K5CBQ hardware, and based on version 2024.03.20.2239

This keyer has a Command Mode rx/tx practice. 
Sometimes, if I train at a speed a little above my comfort level, I experienced that I was never able to transmit the sequence correctly. 
And the keyer just kept hitting me with the same sequence over and over again. 
In desperation, I had to break out of the training mode and restart it again.

Therefore I wanted these modes to give up and move on in a soft way. 
A new variable PRACTICE_MAX_ATTEMPTS  will take care of that. 
A value of 4 means that the keyer moves on to the next word after 4 failed attempts. 
This is the value I use. Other values are: 1 to let it move on at the first failure, and a large value, say 100, 
will give the old behavior where it just keeps hitting you with the same word over and over again.

The modification affects:
* Command Line Interface, Receive / Transmit Echo Practice:
  * Progressive 5 Character Groups
  * callsigns
  * 2,3,4 letter words
  * QSO words 
* Command Line Interface, Keyboard Interactive Receive Practice

Search for "LA3ZA Training" in the Arduino IDE to find the 11 places affected in the code (10 in k3ng_keyer.ino and 1 in keyer_settings_k5cbq.h)

See also [Groups.io discussion in april 2024](https://groups.io/g/radioartisan/topic/105448040)

