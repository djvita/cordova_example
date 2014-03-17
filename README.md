cordova_example
===============

Apache Cordova 

Create android apps with the apache cordova api

This is an empty example of making an android app with cordova.
Using Ubuntu 13.10

Requirements:

-ANT

    sudo apt-get -u install ant

-JAVA; 2 ways

1. Through oracle:
    http://www.oracle.com/technetwork/java/javase/downloads/index.html
Download the jdk, unpack, install in /usr/lib/jvm

2. Through ppa openjdk
    sudo apt-get install openjdk-7-jre
or

    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java7-installer
    
(I did both since openjdk did not come with /lib wich is necessary for building the app; ppa gave error installing ; I downloaded the oracle package, and added the missing files)

-Android SDK
http://developer.android.com/sdk/

Download the full one, comes with eclipse. or follow the instructions to add the plugin to an existing eclipse installation.


-NODEJS
    http://nodejs.org/
nice big install button!

-Cordova
    sudo npm install cordova
or phonegap- 
    sudo npm install -g phonegap

For Cordova command-line tools to work, you need to include the SDK's tools and platform-tools directories in your PATH
environment. On the terminal, you can use a text editor to create or modify the ~/.bash_profile file
      sudo gedit .bashrc
add the following lines at the end of the file:
    
    PATH=$PATH:$HOME/.rvm/bin # Add RVM to PATH for scripting

    export ANDROID_HOME="$HOME/adt-bundle/sdk/tools"
    export ANDROID_PLATFORM_TOOLS="$HOME/adt-bundle/sdk/platform-tools" #CHANGE TO YOUR APPROPIRATE DIRECTORY WHERE YOU INSTALLED ANDROID TOOLS
    export PATH="$ANDROID_HOME:$ANDROID_PLATFORM_TOOLS:$PATH"

    export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-i386 
    export PATH=$JAVA_HOME/bin:$PATH

save,
now

    source ~/.bash_profile
    
logout/reboot machine.

MAKE APP

    $ cordova create hello com.example.hello "HelloWorld"
    $ cd hello
    $ cordova platform add android # here you may encounter problems, only need to do it once, android sdk installed and corerctly pathed!
    $ cordova build # here you may encounter problems, ant and java must be installed and correctly pathed!
    
if you followed everything above, there should be no errors. if there are, its all because of missing packages or the paths. did some troubleshooting and its all there in the .bashrc;
again put this:

    export ANDROID_HOME="$HOME/adt-bundle/sdk/tools"
    export ANDROID_PLATFORM_TOOLS="$HOME/adt-bundle/sdk/platform-tools" #CHANGE TO APPROPRIATE DIRECTORY WHERE YOU AHVE INSTALLED ANDROID TOOLS
    export PATH="$ANDROID_HOME:$ANDROID_PLATFORM_TOOLS:$PATH"

    export JAVA_HOME=/usr/lib/jvm/java-7-openjdk-i386
    export PATH=$JAVA_HOME/bin:$PATH

Once created, you can use the Eclipse that comes along with the Android SDK to modify it:

Launch the Eclipse application.

Select the New Project menu item.

Choose Android Project from Existing Code from the resulting dialog box, and press Next: 

Navigate to hello, or whichever directory you created for the project, then to the platforms/android subdirectory.

Make sure both hello and hello-CordovaLib projects are selected to be imported. The hello-CordovaLib project is needed as of Cordova 3.3.0 because Cordova is now used as an Android Library instead of a .jar file.

Press Finish.

Now start coding in HTML, CSS and Javascript 
