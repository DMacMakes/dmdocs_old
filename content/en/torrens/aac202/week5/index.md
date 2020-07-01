---
title: "5: ZBrush"
linkTitle: "W.5 ZBrush"
weight: 60
description: >
  ZBrush is a critical tool for modern games studios; it's also the best way to sculpt on a computer.
---

## Download And Install ZBrush

* Using 30 day trial for now:
* Working on floating licenses outside uni

Download link on the resources page:

<a class="btn btn-lg btn-primary mr-3 mb-4" href="../resources/#zbrush">Resources<i class="fas fa-arrow-alt-circle-right ml-2"></i>
</a>

### Class Working Files

ZBrush demo scene, template scene and config files.
<a class="btn btn-lg btn-primary mr-3 mb-4" href="aac202_zbrush_resources.zip">AAC202 ZBrush Resources<i class="fas fa-arrow-alt-circle-right ml-2"></i>
</a>

{{< imgproc zbrush_trial Resize "600x">}}
ZBrush 2020.1
{{< /imgproc >}}

## Digital Sculpting?

* What is sculpture (some classical, modern pics)
* Isn't Maya 3D sculpting?
  * Technically, sure
  * In practise it's focussed on points and edges and faces It uses transforms.
  * Generally useful in the < 100K polygons space
(One pic of Maya with smoothed object, maybe joystick)

{{< imgcard maya_app_witcher >}}
The Witcher 3 by CD Projekt S.A.
{{< /imgcard >}}

* ZBrush 
  * Focussed on smooshing and building and carving surfaces
  * Provides tools  a sculptor would recognise
  * Tries to automate the polygon part away
  * Happily works with millions of "polygons" by using a different paradigm internally

{{< imgcard zbrush_app_goblin >}}
Goblin by <a href="https://www.youtube.com/watch?v=Zp07GW3rND0" target="_blank">Flipped Normals</a>
{{< /imgcard >}}

{{< imgcard brushes_additional Link "brushes_additional.jpg" >}}
Many kinds of sculpting brushes
{{< /imgcard >}}

{{< youtube L6kYhShKXKY >}}

### From Film To Games

Many wrinkly monsters, festy zombies and gnarled trees in film have been created with ZBrush.

* When it was first made, games couldn't integrate ZB level 3D except in cinematics
* Won Oscar for contribution to film effects
* GPU accelerated normal maps came along, you could now steal the details from those high res models and approximate them on game models.
* Unreal engine (and whatever doom 3 was on??)

### Doom 3
  
{{< imgcard doom_3 Link "doom_3.png">}}
Doom 3, maybe the first big normal mapped game
{{< /imgcard >}}

{{< imgcard doom_3_2 Link "doom_3_2.png">}}
Doom 3 again
{{< /imgcard >}}

### Doom Eternal

Very current normal mapped assets

{{< imgcard doom_eternal_marauder Link "doom_eternal_marauder.jpg">}}
{{< /imgcard >}}

{{< imgcard doom_eternal Link "doom_eternal.jpg">}}
{{< /imgcard >}}

{{< imgcard doom_cyberdemon Link "doom_cyberdemon.jpg">}}
Original Cyberdemon Zbrush sculpt
{{< /imgcard >}}

## Intro to ZBrush

Using ZBrush on the uni computers or your own.

* Open a **STARTING SCENE I PROVIDE**
* Import the settings I give out (basic right click nav, not saving undo)
* Navigate
  - Right drag tumble
  - Right drag shift snap top/front/left etc
  - alt-right-drag pan
  - ctrl-right-drag zoom
* Save settings.

First marks:
* On provided sphere
* Standard brush: `b, s, t`
* Dam standard: `b, d, s`
* Move brush: `b, m, v`

{{< imgcard brushes_default Link "brushes_default.jpg" >}}
What you'll see when you press `b`
{{< /imgcard >}}

Brush controls:

Press space to access brush controls near the cursor.

{{< imgcard space_menu >}}
{{< /imgcard >}}

Adding mass:
* Still on sphere
* Clay buildup `b, c, b`
* Inflate `b, i, n`
* Smooth brush `shift`
* Snake hook `b, s, h`

More cleaning, subtools:
* Trim Dynamic `b, t, d`
* HPolish `b, h`
* Pinch (on dam standard) `b, p, i`
* Switch to cube subtool, solo.
* trim dynamic, hpolish the corners
* Now smooth, pinch

Pixelation?? Subdivision up down
* Subdivide: `Ctrl + D`
* Step up, down `d`, `shift+d`

## Free play

Play around and make a madball for 25 mins. 

[Screenshot it and post it here](https://laureate-au.blackboard.com/webapps/discussionboard/do/message?action=list_messages&course_id=_89547_1&nav=discussion_board_entry&conf_id=_152757_1&forum_id=_866557_1&message_id=_2191233_1)
  
{{< imgcard madballz Link "madballz.png">}}
Madballz
{{< /imgcard >}}
  
## More Basics

Auto masking:
* switch to skinny object
* Show how sculpting damages back faces
* Backface auto masking
* Inflate brush (without backface mask)

Different Materials:
* how materials affect our perception: detail pops when shiney, not matte.
* Stylised materials a little
* Colours vs material

Getting Out Of Trouble
* things aren't moving - Lost edit mode (hit t)
* 

Watch out:
* Exiting edit mode by mistake (T)
* Getting back into it.

## Due This Week

Homework: Pick one of the madballz (the real foam ball, not a 2D  drawing from their site) and sculpt it as faithfully as you can in 2 hours. The base of your sculpt is the sphere in Trying_Out_Brushes.zpr. If you overwrote it, get a fresh copy from aac202_zbrush_resources.zip](aac202_zbrush_resources.zip).  Use brushes like the standard, dam standard, pinch, inflate, move, hpolish and smooth to reproduce the  clean surfaces and creases. 

{{< alert title="Deliverables and Submission" color= "primary" >}}
Reply to the `Module 5/Homework: Madballz` thread [on the subject discussion forums](https://laureate-au.blackboard.com/webapps/discussionboard/do/message?action=list_messages&course_id=_89547_1&nav=discussion_board_entry&conf_id=_152757_1&forum_id=_866557_1&message_id=_2191238_1). Post the **reference** of your chosen madball along with some **screenshots of the finished sculpt.** Have it done and posted **before next week's class**.
{{< /alert >}}

_**Bonus:**_ ZBrush has a super helpful filter called **Clay Polish**. Look it up in the zbrush documentation or on youtube. To try it out, add some random shapes to your free-play sculpt and hit Clay Polish. For this kind of sculpt it's a bit of a magic "make art" button.

{{< imgcard mb_detail_skullface Link "mb_detail_skullface.jpg">}}
Skullface Detail
{{< /imgcard >}}

{{< imgcard mb_views_skullface Link "mb_views_skullface.jpg">}}
Skullface
{{< /imgcard >}}

{{< imgcard mb_detail_slobulus Link "mb_detail_slobulus.jpg">}}
Slobulus Detail
{{< /imgcard >}}

{{< imgcard mb_views_slobulus Link "mb_views_slobulus.jpg">}}
Slobulus
{{< /imgcard >}}

{{< imgcard mb_detail_hornhead Link "mb_detail_hornhead.jpg">}}
hornhead Detail
{{< /imgcard >}}

{{< imgcard mb_views_hornhead Link "mb_views_hornhead.jpg">}}
Hornhead
{{< /imgcard >}}

{{< imgcard madballz Link "madballz.png">}}
Madballs
{{< /imgcard >}}

<!-- 
## Assessment 2: Character Sculpt

* What to make
* Milestones/deliverables
* Baldy character head
* Or keycap/artisan
-->
<!--
### Today, Pick Concept

Offer selection.
If your own character's head is very well realised in multiple angles, you can make them (without hair)
-->

## Learning Resources

#### Great sculpts

A playlist of great sculpts, many of them timelapsed to <10 mins. Most of them were added over a year ago but they're no less great.

https://www.youtube.com/watch?v=e4LjwgFV8xw&list=PLfWza-ietxyywGqWIFLIuDeBK7DZ7Sych

{{< imgcard sculpts_preview_follygon_troll Link "https://www.youtube.com/watch?v=e4LjwgFV8xw&list=PLfWza-ietxyywGqWIFLIuDeBK7DZ7Sych">}}
One of the great vids by Follygon in this playlist.
{{< /imgcard >}}


#### Standard Brush with Michael Pavlovic

{{< youtube Rm5ZWj1h9GI >}}

#### Brush Palette and Move Brush

{{< youtube fb7WHVhKxu8 >}}

<!--
### Docs

Link to key zb docsumentation

### Videos
Link up:
ZClassroom (specific videos)
Michael Pavlovic Intro
Shane Olsen (does a sculpt in 3 hours each stream with Pixologic)
Follygon

-----
-->
