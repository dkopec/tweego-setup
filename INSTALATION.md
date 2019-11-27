## Installing Tweego

On most versions of Windows, you can use [this installer](https://github.com/ChapelR/tweego-installer/releases) to set up Tweego instead of installing it manually. If you cannot use said installer or prefer to set it up manually, carry on with these instructions.

Installing Tweego globally is probably your best bet.  You can also install it locally, which has some benefits.  I won't cover the latter right now, but it may be added in the future.

These instructions are for Windows 10.  Windows 7 follows a similar process, but you'll need to add to the path variable manually.  This guide may help you get started on other operating systems, too.

### Step 1: Download Tweego

![alt text](https://i.imgur.com/VhjWCad.png)

You can grab both Tweego and a collection of Twine 2 formats from [Tweego's site](http://www.motoslave.net/tweego/).  You may need to update some of the story formats in the collection.  Regardless, download both and unzip them.

### Step 2: Find a home for Tweego

You can put Tweego anywhere, but the simplest places that are closest to your main drive's root are probably best.  I usually put my stuff right on C.

![alt text](https://i.imgur.com/zExCubX.png)

I create a folder called `tweego`, then place the tweego binary and the `story-formats` folder inside it.

![alt text](https://i.imgur.com/BEMfQaw.png)

Just to be safe about it, make sure that the inside of the `story-formats` folder looks something like this.

![alt text](https://i.imgur.com/8skfhb4.png)

### Step 3: Adding Tweego to you PATH

Next we'll need to add Tweego to out PATH environment variable.  You'll need to go to the `System` section of your control panel.  You can search for it.  In the picture below, it's the second option.

![alt text](https://i.imgur.com/BWA8QDF.png)

Go to `advanced system settings`.

![alt text](https://i.imgur.com/kjGOVGb.png)

Click `environment variables` on the bottom right.

![alt text](https://i.imgur.com/jmOwmFa.png)

Under `system variables` at the bottom, find `Path`.  Highlight it and press `edit`.

![alt text](https://i.imgur.com/HTS76WV.png)

On the resulting screen, click `new` on the top right.

![alt text](https://i.imgur.com/6C69SoU.png)

Type in the path to the folder containing tweego.  If you did this like I did, you'll type in `C:\tweego\`.

![alt text](https://i.imgur.com/7rDJ22z.png)

Click OK when you're done, but don't close the Environment Variables window yet!

### Step 4: Add the TWEEGO_PATH variable

This step is optional but recommended.  You may as well do it while you're here to prevent potential headaches later.

Back in the Environment Variables window, click `New`.

![alt text](https://i.imgur.com/LnZ3chF.png)

Set the variable name to `TWEEGO_PATH` and the value to the path that leads to your `story-formats` folder.  If you set it up the same way I did, that path will be `C:\tweego\story-formats`

![alt text](https://i.imgur.com/vJrHaLe.png)

### Step 5: Testing Tweego

Open a command prompt and type `tweego`.  If the command is unrecognized, something was messed up, otherwise, an explanation of tweego should print out.  Type in `tweego --list-formats` to make sure you've installed all the formats correctly and set up `TWEEGO_PATH` correctly.  It should display all the formats you have in your `story-formats` directory.

## Installing NodeJS

You can install node from [here](https://nodejs.org/en/).  You want to grab the LTS version, usually the one on the left.  This will download an msi file, that will then install node on your system.

The only thing to watch out for when installing Node is to make sure that it is added to your path, and that you include npm.  By default, both of these options will be enabled.  For best results, install node on your main hard drive (usually C) with your operating system.

![alt text](https://i.imgur.com/uaXMM9k.png "Make sure to include npm and add to path!")

To make sure eveything works, you can open a command prompt and type `npm`.  If the command isn't recognized, you've messed up!  Otherwise, a help message explaining npm should display.


## Installing Gulp (Optional)

The core of this build system is based on the task-runner Gulp, which just makes things a little smoother for us.  This setup uses Gulp locally already, but if you want to mess around with it more, you'll probably want to globally install it.  You can do so with the following command:

`npm install --global gulp`

After doing so, you'll want to look at the `gulpfile.js` file to define new tasks or alter old ones.  When installed globally, you can run gulp tasks directly, without needing to go through npm.  So `npm run gulp build` becomes `gulp build`.

Again, installing gulp globally isn't required to use this setup.

## Updating tweego-setup

To update your build system in an ongoing project, replace the `package.json` and `gulpfile.js` files with the new versions, then delete the `node_modules` folder and the `package-lock.json` files and run `npm install` from the command-line. You can also optionally delete the `.babelrc` file if it exists, as it is no longer used, but it won't hurt anything either way. 

I recommend backing up your old version via a version control system (like GitHub or BitBucket) so that you can revert the changes if things go wrong. If you don't or can't and things do indeed go wrong, saving a copy of the old `package.json` and `gulpfile.js` files is enough for you to revert back using the same process outlined above.

You can check which version you currently are using and which version is the latest available in this repo in the `package.json` files, right up near the top.

> Note: If you update to tweego-setup v2.0.0 or higher, you need to be sure to update to Tweego v2.0.0 or higher.