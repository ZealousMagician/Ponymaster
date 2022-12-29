# Ponymaster
### This is a collection of dynamic prompts to allow anyone to create images with high quality, randomised pony-specific prompts.

### Here you'll find information about how to use Ponymaster, as well as credits and a changelog at the end.

Ponymaster runs on the Unprompted extension (last update: 4.3.0), which allows you to input [file x/y] in the prompt to run files at a specified location, with its own sort of code and wildcard system. "poma" is just short for Ponymaster in the files.
To set Ponymaster up, first ensure you have unprompted installed, either through the webui extensions tab (make sure you unhide extensions with ads), or download it from https://github.com/ThereforeGames/unprompted. Once you've done that, move the "poma" folder to the templates folder in unprompted.

Ponymaster is tested on and intended for use with Astraliteheart's V3.1 pony model, or alternatively a custom merge containing V1 and V2 if you do not have access to V3.
To create the custom model:
- Download the V1 and V2 pony model, as well as the Wikiartv2 model (these can be located at https://rentry.org/sdmodels)
- Merge the pony V1 model with the Wikiartv2 model, 85% Pony V1 to 15% wikiartv2. (customv1)
- Merge the customv1 model with the pony V2 model, 75% customv1 to 25% pony V2. This will give you the model (customv2) that outputs the best results with Ponymaster if you do not have access to pony V3.1
- If you have access to pony V3.1 and wish to create 512x512 images, or to achieve the highest quality for the upgrade feature, then merge the customv2 model with pony V3.1, 75% customv2 to 25% pony V3.1. This will give you the ideal model for 512x512 image generation with Ponymaster. Keep in mind that Pony V3.1 at 768x768 is better in quality than the custom merge at 512x512; the exception being with the use of the upgrade feature for img2img which is further explained later in this document.


To start, simply type "[file poma/main]" into the prompt field to run the main branch of Ponymaster. This will create images of random ponies doing random things in many different styles- most of which being high quality. The only settings you need to change are the width and height (if you're not sure, 512x512 for v1/v2/custom models, 768x768 for v3.1), the batch count and batch size, and the checkpoint/model being used.
If you're running a large batch, it may take a minute for stable diffusion to actually start. This is normal, although likely due to poor optimisation on my part.

Other prompts and files of note are explained below.

- **[file poma/finisher]**: Similar to poma/main, but it allows you to input a short description of what you want at the start, rather than it randomly selecting a pony. An example is "Blue pegasus wearing a purple jacket, [file poma/finisher]"

- **[file poma/experimental]**: Similar to poma/main, but chooses between three different randomized prompts across either the main or trippy variant, which randomly combines two styles, combines two superartists, or combines three artists from a very long list. Useful for if you want to find completely new styles or superartists.

- **[file poma/upgrade]**: This is used exclusively for img2img. This file contains a list of prompts which apply various high-quality/novel styles to the image, and can be used to turn a pony in an image into a lifelike plushie, a 3d render, an anime artwork, and more. It also automatically changes the negative prompt and settings for img2img. If you know what you're doing, there's a notes file describing each of the prompts' styles, and you can adjust the denoising strength to suit your needs.
Something important to note is that the custom merge model and pony v3.1 model seem to be of similar quality for 768x768 resolution img2img upgrades, otherwise the custom merge seems superior for 512x512 here.
Take a look at poma/upgradenotes for information regarding each prompts' style and optimal settings.
[file poma/preset] is the same but for regular txt2img prompting. In my limited testing I've found it doesn't have great outputs, but your results may vary.

- **[file poma/negative]**: The negative prompt file, which contains a (painstakingly-crafted) negative prompt. This is usually automatically applied when using Ponymaster. It also has an alternate prompt which you can enable- open the file for more info.

- **[file poma/settings]**: The settings file- it changes steps to 45, sampler to Euler a, and CFG scale to a number between 14.5 and 15.5 (15 seems to be the optimal amount, but I've set it to a small range around that number just for fun and slightly more variation). This is usually automatically applied when using Ponymaster. Note that while CFG is slightly randomized between generations, it is not randomised between batches like other parts of Ponymaster due to a limitation of the Unprompted extension.

- **[file poma/superartist]**: This contains a large amount of combinations of artist names that create entirely unique styles that have a large impact on the prompt. If you have no interest in the rest of Ponymaster, it's still a good idea to take a look at this list and see if any of it appeals to you for your own prompts. Important note: None of these are pony fandom artists.

- **[file poma/trippybranch]/[file poma/trippybranchfinisher]/[file poma/trippybranchexperimental]**: This is the "trippy" branch for the main, finisher, and experimental prompts. The outputs here vary more in quality and style, and have some fun additions.

- **[file poma/fun]**: This is the "fun" list, which contains a collection of strange prompt modifiers such as "made of cobwebs", "made from Felt fibers, made of yarn", and "regalia". It currently only exists within the trippy prompts.

- **[file poma/style]**: This contains a wide variety of styles, some of which are combinations.


Ponymaster was made by Zealousmagician, with some minor support from Yossarian.

---------------------------------------
Changelog:

V1.0: Initial release!
