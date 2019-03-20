![](assets/cover.png)

# Parametric-Design
Code-basics scipted in MEL & PYTHON in the [Autodesk Maya](https://en.wikipedia.org/wiki/Autodesk_Maya) environment.

Are you ever curious to dive into programming in Maya? Are looking to take your work to the next level and challenge yourself and explore new opportunities by explorations in creativity through the practice of programming? – then start with generative design in Maya

Inspired by [Kostas Terzidis](https://github.com/imkostas?tab=repositories) class „Parametric Design“ and some projects & experience I did before at the [HfG Schwäbisch Gmünd](https://www.hfg-gmuend.de/) I started this Repository to share my experience and Insights.  
Here I will provide you with some Basics to start so you can get familiar with scripting in Maya. In addition I try to provide more and more code snippets in MEL & Python – stay tuned!





# Lets Get Started

Open Maya and find the Mel and Python Editor. Click on the icon in bottom-right corner 

![](assets/Editor_icon.png)

If you don‘t see it? – Then got to ```WINDOWS → GENERAL EDITORS → SCRIPT EDITOR```

![](assets/Editor.png)

## Step One – Monitoring the Command History

This History will be your best friend! Amazingly Maya is printing here almost all actions that you perform in the UI. So you create a cube just by using the normal UI and the history will show you the MEL command for the used action. In addition the Command History displays any feedback such as results, warnings, or errors returned by Maya.


![](assets/History.png)

## Step Two – Copy & paste

Now you can start creating something new by copy and paste commands to create your own worklfow. Just copy from the History panel the commands you need and paste in the Editor panel to piece together your custom automation work flow.

<p align="center">
  <img width="460"  src="https://camo.githubusercontent.com/d990f75ee78efb887d9c833b77493cf44606a018/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f78484d4944417931716b7a4e532f67697068792e676966">
</p>

## Step Three – Memorize documentation

To look up the different commands you can find these in the Help Documentation, → hot-key F1.

**[→ Help Documentation](http://download.autodesk.com/us/maya/2011help/Commands/)**


## Step Four – Saving your mind blowing Snippets

Once you have put together a script, you can drag it into the shelf inside the Maya UI to save it for later and re-use it over and over. Highlight, Press 'Alt' and drag the script into the Shelf tab of your choice (If u closed ur Shelf tab) Windows->UI Elements->Shelf

![Script into Shelf](assets/intoshelf.gif)


***Or*** Just add a line of code into your Script – ```scriptToShelf  ("MyFirst", "select -all", true);```

```
file -f -new;
polySphere -ch on -o on -r 7;
nurbsCube -p 0 0 0;
polySphere -ch on -o on -r 2.5;

select -r pSphere1 nurbsCube1 pSphere2;
group;

scriptToShelf  ("MyFirst", "select -all", true);
```



---
Useful Links 
  * [Maya tutorial – bournemouth](https://nccastaff.bournemouth.ac.uk/jmacey/RobTheBloke/www/maya/)



