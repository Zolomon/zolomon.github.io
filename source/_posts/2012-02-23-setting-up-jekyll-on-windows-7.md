---
layout: post
title: "Setting up Jekyll on Windows 7"
category: tutorial
tags: [blog, how to, jekyll]
---
# How I installed Jekyll on Windows 7

## Step 1: Install [Ruby with the RubyInstaller](http://www.rubyinstaller.org/downloads/)
Download and install Ruby (I chose [rubyinstaller-1.9.3-p125.exe](http://rubyforge.org/frs/download.php/75848/rubyinstaller-1.9.3-p125.exe)).
Then [download and unzip the DevKit](https://github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe) version of Ruby from the same page.
### How to [install the DevKit](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit)
While installation is (in general) simple, please ensure you carefully follow each step below.

#### 1. Preparation

If you previously installed the legacy DevKit devkit-3.4.5r3-20091110.7z, its artifacts were extracted into each Ruby installation and need to be manually removed. Remove the gcc.bat, make.bat, and sh.bat stub batch files in ```<RUBY_INSTALL_DIR>\bin``` and the ```<RUBY_INSTALL_DIR>\devkit``` subdirectory for each Ruby installation using the legacy DevKit.
If you previously installed one of the legacy self-extracting DevKit’s, follow the SFX DevKit upgrade instructions.

#### 2. Download Files
The current DevKit is available at the RubyInstaller download page with older versions available at the archives page. As backup, check our GitHub downloads page.

#### 3. Extract Files

Left double-click the self-extracting executable (SFX) downloaded from Step 2 and choose a directory (without spaces) to install the DevKit artifacts into. For example, ```C:\DevKit```. NOTE: the SFX is really a 7-Zip archive with a bit of embedded magic. If you already have 7-Zip installed, you can simply right-click it and extract it’s contents as you would a normal 7z archive. In the instructions that follow, the directory that you selected is identified as ```<DEVKIT_INSTALL_DIR>```.

#### 4. Run Installation Scripts

```cd <DEVKIT_INSTALL_DIR>``` from Step 3 above.
ruby dk.rb init to generate the ```config.yml``` file to be used later in this Step. Your installed Rubies will be listed there (only those installed by a RubyInstaller package are detected at present).
edit the generated config.yml file to include installed Rubies not automagically discovered or remove Rubies you do not want to use the DevKit with.

[optional] ```ruby dk.rb review``` to review the list of Rubies to be enhanced to use the DevKit and verify the changes you made to it are correct.
finally, ```ruby dk.rb install``` to DevKit enhance your installed Rubies. This step installs (or updates) an ```operating_system.rb``` file into the relevant directory needed to implement a RubyGems pre_install hook and a ```devkit.rb``` helper library file into ```<RUBY_INSTALL_DIR>\lib\ruby\site_ruby```. NOTE: you may need to use the ```--force``` option to update (with backup of the originals) the above mentioned files as discussed at the SFX DevKit upgrade FAQ entry.

#### 5. Test Installation

Confirm your Ruby environment is correctly using the DevKit by running gem install rdiscount --platform=ruby. RDiscount should install correctly and you should see Temporarily enhancing PATH to include DevKit... in the screen messages. 

Next run ```ruby -rubygems -e "require 'rdiscount'; puts RDiscount.new('**Hello RubyInstaller**').to_html"``` to confirm that the rdiscount gem is working.

## Installing [Jekyll]()
Install Jekyll using ```gem install jekyll``` in your command prompt.

## Clone [Jekyll Bootstrap](jekyllbootstrap.com)! 
Go to the Jekyll Bootstrap website and follow the instructions there, then you're done!
