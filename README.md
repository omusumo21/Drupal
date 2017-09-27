Archive opencharities.zip copy from ftp.

For the job I installed a distribution for Drupal 7.56 without any additions.

For each part of the page I have created separate modules (they are all controlled from the category "modules", are placed on the page using the standard menu "blocks")

Each module is written in pure javascript (without jQuery) and php code is in files ...-block.tpl.php / page.tpl.php

In addition to ease of management, I also tried to automate the calculations of each object regardless of the relationship to the browser features of css (the main thing that has javascript enabled).

Description of modules:

1. background. 
Faceromance stretches the background image, aligning it in the center ( this is the most obvious solution, given the "narrow" picture).
In module settings you only need to write the name of the image file (for example, image.jpg). A picture must be put in the images folder.

2. pretext. 
Text module (nothing special) - just two fields for h2 and free HTML code (located in front of a fixed picture in the beginning of the page)

3. Event.
The module displays closest to the actual date of the event. 
Registration form - send a standard form, send to specified mailbox, the email entered into the form data. 
In the module settings: date, space for comments (e.g., time of the event), an event name, a link to the events page.

4-5. features menu 
Two modules where you can enter the name of the pictures, links, alt text (in the order presented on the page).
Autovaruosade height (focusing on the most "high") is necessary, as the length of the text in different blocks is different.

6. logo-carousel. 
This module takes the width of the container, automatically selecting the appropriate number of logos in the slide.
Calculates and sets suitable for the screen logo sizes (width and height).
Here is added the image alt and link.

7. blog slider.
Selects records from database (table news).
Sorts by date modified (displays starting with newest)
Trims the text to 150 characters.
Automatically switch slides.
Aligns the text part, both in width and height.
Nothing to configure.

8. SMM - it's simple: you only need to enter in the settings class from font-awesome, alt, and link.

Tried to follow the BEM methodology. Version .less lies at the root of the folder in css. (the demo page works on the compiled less - when connecting less.js unstable is compiled on the client)

When you click on the link of the current page in the main menu is scrolling down to the block with the main content (OUR MISSION)


This is my first experience with drupal, as well as the first independently written modules in php and javascript (I used to only typeset and modified the existing code).
Will list bugs that still not fixed:
1. Have not figured out how to disable drupal's automatic conversion of external links to inner.
2. "Smooth" scroll to content when you click on the link in the main menu, and code of send mail (send.php) I found it difficult and so I found them on the Internet.
3. In code Logo-carousel for stable operation had to disconnect the output of the last two logos.
4. In the settings of the plugin there is an unused field modules done on the basis of a model code template module (RSS https://habrahabr.ru/post/200340/). Not turned off to be able to send until 28 September.
5. Font: the photoshop layout was a combination of openSans and museoSans. MuseoSans paid. I replaced it with a free Comfortaa from googleFonts.
