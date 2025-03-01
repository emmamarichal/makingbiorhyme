---
layout: post
title: "Polishing & Proofing"
description: "Kerning, Hinting and all that jazz"
category: articles
tags: [sources, reference, research, starting out]
image: 
 feature: 09_Polishing_Producing.png
---

Although I have left this section till last, this is more a reflection of the chronological order of the process than indicative of the role of these tasks in the process of making a typeface. The reason these tasks are at the end should not imply that they are fast, or mere wrap-up tasks. 

**Kerning**
Earlier on, I discussed spacing and the importance of establishing a good rhythm of black and white in any typeface, with the success or failure of the typeface being equally, if not more so, dependent on this rhythm than even the quality or beauty of the forms of the typeface itself. (A beautiful group of letters rather than a group of beautiful letters.) With this in mind, I will add yet another layer to the importance of good spacing and of spending time on the spacing before tackling any kerning. 

Where spacing tackles the appropriate amount of space to allow on either side of any letter so that it will sit as comfortably as possible with any other letter in random combination, and to feel centered between shapes with a lot of symmetry like the ‘o’, kerning tackles those combinations where the space left around the letter to handle most letter combinations well, needs a little bit of tweaking in certain cases. 

These pairs usually occur along a spectrum of pair-specific adjustment from acute need down where the pair is causing the splitting of a wordshape to splitting-hairs levels of polish and refinement where a kern is used to merely tweak an almost perfect pair. 

Put simply, kerning should be relied upon to correct spacing and improve or finesse fit, and never as a replacement for bad spacing. Here again, spacing is paramount, as a badly spaced typeface will be a badly kerned typeface, and near-impossible to fix without very tricky untangling and tracing back of missteps in the spacing. Best to avoid this by proofing the spacing as much as possible and spending more time here to save time on kerning later, the opposite just won’t work! 

Generally, you want to do as much as you can with spacing alone, to reduce the amount of kerns, which both increase the file size, and slow the release of the typeface since more kerns means more proofing. Once you’ve spaced your typeface, and are confident in its behavior and in the water-tightness of the patter, it’s time to kern. Kerning is made more efficient by the use of kerning ‘classes’ or ‘groups’. These are effectively lists which group together similar shapes based on a left-right axis (ie. left side of the d with the left side of the q, since these letters usually have the same bowl shape) which allows the font to store kerning information according to a look-up formula which looks to see if a letter fits into a particular group or class and then finds the instruction which dictates how this group or class has been defined as intended to sit alongside any other. For example, the left ‘o’ class (o_L) might contain all glyphs which share the profile of the o on its left side at the x-height—things like the c, or e forms—and the right ‘o’ class (o_R) by contrast, all those which share the profile of the o on its right side at the x-height—b, p etc. This way the instruction or kern just needs to be remembered and stored as a formula as follows: when you have any glyph that falls into (o_R), sitting beside any glyph that falls into (o_L) overlap their bounding boxes by X amount. That way, only one value needs to be remembered for multiple possible pairs. 

These groups are often very similar to those used for spacing relationships. Another thing to remember when setting up these groups is the need to include all your accented characters into the group that applies to their parent or base component, and to remember to kern to the non-Latin or extended Latin forms too. Things like the eth and the thorn, and the lslash and dcaron, which if following the model of their parent glyph may collide in virtue of their bar or accent in some combinations and not all. For example the lcaron and the t often collide if there is not an exception made to this formula for these specific forms in combination. 

Exceptions, again, much like the amount of kerns and the amount of points on a curve, should be kept to a minimum and used judiciously. If you find yourself making many exceptions to a particular group combination, it may be better to make another group to include only these glyphs and add these to the proof than to include them in a group for which most behaviors will not reach a positive result.

**Hinting**
Hinting is perhaps the murkier, less transparent end of the type design process, so it bears a little summary explanation here, I think. Hinting is the process of embedding or encoding a set of instructions for the display and printing of a given font into the font metadata. 

Hinting has gone through many evolutions, as screens have improved and printers gain resolution, however, there are still a variety of environments, both print and screen, that fall short of the retina, pixel perfect quality those of us on Macs have come to expect. Browsers too all render text differently depending on the rasterizing algorithms being employed, and so the efficacy and quality of a fonts appearance is still largely at the whim of these factors. With this in mind, designers or often, hinters, test the fonts at a variety of sizes and in these varied environments, to see how the forms respond, and then write instructions for the display engine to execute in the display of the fonts at different sizes. 

Font production and hinting are tasks unto themselves in many type foundries, indeed, hinting is a specialized skill that is often also outsourced in its entirety due to the complexity of the task. However, for BioRhyme, as a typeface designed for display, at larger sizes, hinting played a minimal role in the design itself. 

For typefaces designed for body text-setting and particularly those designed to work across a range of media in a variety of resolution conditions, hinting can make a huge difference in the display of and thus performance of, the typeface itself. In these cases, professional hinting may well be something that should not be integrated only at the end of the project as it was with BioRhyme, but embedded early in the design process in order to optimise and test the forms themselves, and fix as many issues through the design itself, and through the engineering of the fonts outlines themselves as possible. 

For most purposes, however, TTFAutohint, and the autohint function of Glyphs which is built on TTFAutohint, can get you a lot of the way there, providing you have drawn the forms methodically and with relatively standard stems and alignments. From an autohinted font, you can then tweak these hints if you see fit, and the proofing is showing up problems, through a set of ‘Instructions’ which you can input and test through the GUI for TTFAutohint. There is a great tutorial on this here. 