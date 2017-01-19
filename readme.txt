Please contact me if I am missing good bases or if you have any ideas to improve the filter.

//discord : ytv#5924
//reddit : /u/ytvvvv

Loot filter was created for end game in mind.

Hides all grey, white, blue, rare items, but displays the ones listed in filter.
We only want the best possible bases.

Overview of what this filter hides and displays :

*Displays all sets and unis (regadless if they are ETH or not)
*Hides all grey,white,blue, and rare unless it is mentioned below.
*Hiding gold that is less than 2k
*Displaying Stamina pots/keys if your character is lower than level 30. If above it will hide stamina pots/keys
*Displays Full Juv as Rejuv
*Hiding all throwing pots
*Displaying TP book, TP scrolls, ID books, ID scrolls if your character is lower than level 30. If above it will hide TP scroll, TP book, ID scroll, ID book
*Hides all ears
*Displays all flawless gems with a shorten name. Displays all other tier of gems as the normal name with the normal color.
*Displays health pots and mana pots tier 1-3. Hides tier 4 pots. Displays tier 5 pot.
*Displays Perfect and Flawless skulls for rerolling. Hides the rest of the skulls.
*Displays all small charms with ilvl in name
*Hides all large charms excluding ilvl99. Torch is ilvl99, so we will still be able to see torch drop.
*Displays all grand charms with ilvl in name
*Displays all runes.

*Displays flails with 0,4,5 sockets. Will display if it is eth or not. Example, eth flail with 4 socket will come up as "flail [4] [eth]"

*Displays crystal sword with 0,4,5 sockets. Will display if it is eth or not. Example, eth crystal sword with 4 socket will come up as "crystal sword [4] [eth]"

*Displays monarchs with 0, or 4 sockets. Hides eth 0 or 4 socket.

*Displays all ELT polearms with 0,4,5. Will display if it is eth or not. Example, eth thresher with 4socket will come up as "Thresher [4] [eth]"

*Displays Berserker Axe with 0,5,6 sockets. Will display if it is eth or not. Example, eth Berserker Axe with 4 socket will come up as "Berserker Axe [4] [eth]"

*Displays Phase blade with 0,5,6 sockets. Will display if it is eth or not. Example, eth phase blade with 4 socket will come up as "Phase Blade [4] [eth]"

*Displays Dusk Shroud with 0, or 4 sockets. Will display if it is eth or not. Example, eth dusk shroud with 0 socket will come up as "Dusk Shroud [0] [eth]"

*Displays Archon Plate with 0, or 4 sockets. Will display if it is eth or not. Example, eth archon plate with 0 socket will come up as "Archon Plate [0] [eth]"

*Displays Mage Plate with 0, or 3 sockets. Will display if it is eth or not. Example, eht mage plate with 3 socket will come up as "Mage plate [3] [eth]"

*Displays rare circlets, hides white, magical. Updated to display white & eth diadems.
*Displays rare druid pelts. Displays non eth with 0,2,and 3 sockets. Hides eth, and magical.
*Displays rare barb helms. Displays eth/white 0,2,and 3 sockets. Will display if helm is eth or not. Hides magical.
*Displays Greater Talons magical and rare. Hides white.
*Displays Runic Talons magical and rare. Hides white.
*Displays ELT pally shields with res>28 with 0,3,and 4 socket exlcudes ETH. Hides rares and magical.
*Displays Matriarchal Bow with >1 +bow & cross bow skills with 0,or 4 sockets. Hides rares and magical.
*Displays Grand Matron Bow with >1 +bow and cross bow skills with 0, or 4 sockets. Hides rares and magical.
*Displays all staffs excluding the staffs that cannot roll 4 sockets & with only >1 to ES. Shows 0 or 4 socket eth/white. Hides all rares and blues.

*Displays Elder staff - white or ETH with 0 or 4 sockets. Will display if it is eth or not. Example, eth elder staff with 0 socket will come up as "Elder staff [0] [eth] Hides all rares and blues

*Displays Shillelah staff - white or ETH with 0 or 4 sockets. Will display if it is eth or not. Example eth shillelah staff with 0 socket will come up as "Shillelah [0] [eth]" Hides all rares and blues

*Displays Archon Staff - white or ETH with 0 or 4 sockets. Will display if it is eth or not. Example eth archon staff with 4 socket will come up as "Archon Staff [4] [eth]" Hides all rares and blues

*Displays all rare rings. Hides all blue rings
*Displays all rare amulets. Hides all blue amulets
*Displays all jewels
*Displays only rare quivers
*Displays only rare bolts
*Displays uber keys with a shorten name, and the act that they came from
*Displays dust from bosses with a shorten name and the name of the boss it came from
*Displays writs leg


/////////////////////////////////
//////THINGS TO DO OR REVIEW/////
/////////////////////////////////

Magical items have a prefix, a suffix, or both. 
Rare items can have up to six modifiers; 3 suffixes and 3 prefixes, or any combination thereof.

http://diablo2.diablowiki.net/Suffix
http://diablo2.diablowiki.net/Prefix

/////////////////
//////Pelts//////
/////////////////

Druid pelts can spawn with three additional druid skill, and each can vary between +1-3. 

And as a reminder..Prefix - +2druid skills, Prefix +2 to skilltab)

Meaning the following is possible on a RARE pelt :

+2 druid skill (PREFIX) OR +2 to skilltab for druid (PREFIX)
+3 to nado (implicit)
+3 to hurricane (implicit)
+3 to oak sage (implicit)

^This means we are only using 1 prefix at the moment, and can have up to 2 more prefixes and 3 more suffix.

At the moment we have druid pelt code as :
//Druid Pelt// -Shows non-eth 0, 2, or 3 socket. Displays RARE, SET, UNIQUE.
ItemDisplay[CL1 !ETH NMAG (SOCK=0 OR SOCK=2 OR SOCK=3)]: %DGREEN% %NAME% [%SOCKETS%]
ItemDisplay[CL1 (RARE OR UNI OR SET)]:%NAME%

All druid pelts exlcuding eth with 0,2, or 3 sockets will be shown. This is good, but we can probably make this better by making it only show if the pelt has +skills on it. That way we don't have to pick up every single pelt.

Possible example?
ItemDisplay[CL1 !ETH NMAG SK245>0 (SOCK=0 OR SOCK=2 OR SOCK=3)]:.. <- This would display NADO only helms..

so ideally we can do something like this :

ItemDisplay[CL1 !ETH NMAG (SK245>0 OR SK250>0 OR SK226>0) (SOCK=0 OR SOCK=2 OR SOCK=3)]:.. Not sure if this would work. ideally this code represents.. show me any pelt that is white only (hide eths) with skills tornado, or hurricane, or oak sage greater than 0, and it must have either sockets 0,2,3.

ItemDisplay[CL1 !ETH NMAG (SK245>0 OR SK250>0 OR SK226>0) (SOCK=0 OR SOCK=2 OR SOCK=3)]: %DGREEN% %NAME%
ItemDisplay[CL1 (RARE OR UNI OR SET)]:%NAME%

The above code works (tested in hero editor), we simply just need to add all the skills that we want to see on pelts. If the skill is not listed the pelt will not be displayed.

For example let's say we have a white pelt with no stats or skills & it is 0 socket.
The pelt agrees that it is a NMAG item, but it does not have the stats that line is requesting, the pelt does agree it is 0 socket.
Next line stats are you a rare uni or set? The pelt disagrees.

And near the bottom of the filter we have :

//Hide all armor that is grey, white, magical, rare. still shows uni and set items (eth/noneth) (All armor meaning helm, body, shields, gloves, boots, belts, circlets)
ItemDisplay[ARMOR (SET OR UNI)]: %NAME%
ItemDisplay[ARMOR (NMAG OR MAG OR RARE)]:

The filter asks again to the pelt. are you set or uni? No the pelt isn't. Disagress.
Next line states are you nmag, mag and rare? Yes, I am a white pelt (nmag) lists as nothing which will hide the pelt.

So in theory if we have a white pelt with stats that are not listed it will hide the item. We need to ADD all skills that are possible on druid pelts (for white bases only rares doesnt matter)

At the moment I left the druid pelt selection alone. It will display pelts with any stats on white items. Hides ETH white base pelts. Shows white, and rare.