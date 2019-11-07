## "This Java Environment is not supported in Astah."
#### How to install Astah and switch your java-version if necessary.

If you havent downloaded Astah yet, you can do it [here](http://astah.net/download). I downloaded Astah UML, but it might work for the other version as well. If you're a student, press the "Students - Get Free License" button, to get a free license. Otherwise you will only get the normal version, which requires license-key after 30 days of trial. After entering your stundent-information, you can download a license-file and Astah itself. If you are running on Ubunut like me, you're gonna need the Linux<sup>Deb</sup> download.

Once you finished downloading and installing Astah and you try launching it. If it openes without any problems, then you already have the right Java-Version. Then you only need to click "Help" in the options-menu and then "Set License Key", choosing the license-file you downloaded earlier.

#### Downloading and Switching your java-version
If you dont have the correct Java-version, you might get a message like this:
![text](/home/tobi/Privat/GitHub/HowTo/figs/Astah_Java_Version.png)
In that case, you're gonna need to install an older version of java. I decided to install Java 8, which is the version, Astah seems to require. You can download it [here](https://www.java.com/en/download/linux_manual.jsp). I chose the Linux x64 Option for my Ubunut 19.04. machine. Once downloaded, i followed [these](http://astah.net/qa/setup/linux) instructions, which are:

First you have to decompress the downloaded file. In my case, the file name was jre-8u231-linux-x64.tar.gz, so i did:

`$ tar -xvf jre-8u231-linux-x64.tar.gz`
