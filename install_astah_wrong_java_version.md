## "This Java Environment is not supported in Astah."
#### How to install Astah and switch your java-version if necessary.

This worked for Ubuntu 19.04. on my machine.

If you havent downloaded Astah yet, you can do it [here](http://astah.net/download). I downloaded Astah UML, but it might work for the other version as well. If you're a student, press the "Students - Get Free License" button, to get a free license. Otherwise you will only get the normal version, which requires license-key after 30 days of trial. After entering your stundent-information, you can download a license-file and Astah itself. If you are running on Ubuntu like me, you're gonna need the Linux<sup>Deb</sup> download.

Once you finished downloading and installing Astah and you try launching it. If it openes without any problems, then you already have the right Java-Version. Then you only need to click "Help" in the options-menu and then "Set License Key", choosing the license-file you downloaded earlier.

#### Downloading and Switching your java-version
If you dont have the correct Java-version, you might get a message like this:

![](figs/Astah_Java_Version.png)

In that case, you're gonna need to install an older version of Java. I decided to install Java 8, which is the version, Astah seems to require. You can download it [here](https://www.java.com/en/download/linux_manual.jsp). I chose the Linux x64 Option for my Ubunut 19.04. machine. Once downloaded, i followed [these](http://astah.net/qa/setup/linux) instructions, which are:

First you have to decompress the downloaded file. Move to the file location within your terminal and enter:

`tar -xvf <filename>.tar.gz`

In my case, the file name was "jre-8u231-linux-x64.tar.gz" so i entered:

`tar -xvf jre-8u231-linux-x64.tar.gz`

That created a folder, named "jre1.8.0_231". Now you have to move the folder to the right place, in order for this Java-version to be recognized. The next command will move the folder to the right position and rename it to "jdk1.8.0" at the same time. You do that by typing:

`sudo mv ./jre1.8.0_231 /usr/lib/jvm/jdk1.8.0`

After that, you need to run the following 3 commands. Dont worry if one or more throw an error/warning. They did, when i entered them, but it worked nontheless. Just be careful to type exact (or copy and paste) or it might say something like "error: alternative link /usr/bin/java is already managed by java". The only things that change between each line, is the "java" in the middle and the "/java" at the end of each line.

````
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0/bin/java" 1
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.8.0/bin/javac" 1
sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/lib/jvm/jdk1.8.0/bin/javaws" 1
````

Now, you should be good to go. The final step is to switch to the Java-version of your choice with:

`sudo update-alternatives --config java`

It will open up a menu, looking like this: 
````
Selection Path Priority Status
--------------------
* 0 /usr/lib/jvm/java-12-openjdk-amd64/bin/java 1211 auto mode
1 /usr/lib/jvm/java-12-openjdk-amd64/bin/java 1211 manual mode
2 /usr/lib/jvm/jdk1.8.0/bin/java 1 manual mode

Press enter to keep the current choice[*], or type selection number: 2
````

The &ast; indicates the version you are currently at. You only need to choose the number for Java 8 (jdk1.8.0) which in this case is number 2. If you want to switch back, just use the same command and the number it had before.

I personally set up an alias called "javaversion" in my ".bashrc" file, so i dont have to remember the command above. That way, i simply have to enter "javaversion" in my terminal, to get in the menu, where i can switch the version. If you dont know, how to create oder edit aliases, unfortunately you're gonna have to look that up yourself.

And that's it. I hope it helped one or the other person, beeing able to use Astah.

Sources:
- [http://astah.net/download](http://astah.net/download)
- [http://astah.net/student/thank-you](http://astah.net/student/thank-you)
- https://www.java.com/en/download/linux_manual.jsp 
- https://www.java.com/de/download/help/linux_install.xml (german) 
- http://astah.net/qa/setup/linux 
