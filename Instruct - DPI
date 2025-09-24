Note : Its only for educational purpose never download any pirated software such as burp or anything its for DPI resizing purpose 

### Script to download and install burp 

save as install.sh

```
#!/bin/bash

# Installing Dependencies
echo "Installing Dependencies..."
sudo apt update
sudo apt install git axel openjdk-17-jre openjdk-21-jre openjdk-22-jre -y

# Cloning
git clone https://github.com/xiv3r/Burpsuite-Professional.git 
cd Burpsuite-Professional

# Download Burpsuite Professional
echo "Downloading Burp Suite Professional Latest..."
version=2025
url="https://portswigger.net/burp/releases/download?product=pro&type=Jar"
axel "$url" -o "burpsuite_pro_v$version.jar"

# Execute Key Generator
echo "Starting Key loader.jar..."
(java -jar loader.jar) &

# Execute Burpsuite Professional
echo "Executing Burpsuite Professional..."
echo "java --add-opens=java.desktop/javax.swing=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm.Opcodes=ALL-UNNAMED -javaagent:$(pwd)/loader.jar -noverify -jar $(pwd)/burpsuite_pro_v$version.jar &" > burpsuitepro
chmod +x burpsuitepro
cp burpsuitepro /bin/burpsuitepro
(./burpsuitepro)

```


### FOR proper DPI create a launcher to launch the burp suite from the working directory in where it is located!

1. Create the file

Run this in your terminal (it will create the launcher in your user’s application folder):
```
mkdir -p ~/.local/share/applications
nano ~/.local/share/applications/burpsuite-pro.desktop
```

2. Paste this content

Inside the editor, paste:

```
[Desktop Entry]
Name=Burp Suite Pro
Comment=Launch Burp Suite Professional with correct DPI
Exec=/bin/bash -c "cd /root/Desktop/Tools/Others/Burp/Burpsuite-Professional/Burpsuite-Professional && ./burpsuitepro"
Path=/root/Desktop/Tools/Others/Burp/Burpsuite-Professional/Burpsuite-Professional
Terminal=false
Type=Application
Categories=Development;Security;
Icon=applications-development
```
Save and exit (CTRL+O, ENTER, CTRL+X if using nano).

3. Make it executable
```
chmod +x ~/.local/share/applications/burpsuite-pro.desktop
```

4. Refresh desktop database

Depending on your desktop environment, run:
```
update-desktop-database ~/.local/share/applications
```

5. Run it

Now you should see “Burp Suite Pro” in your app menu.
If you want the icon directly on your desktop, copy it there:

```
cp ~/.local/share/applications/burpsuite-pro.desktop ~/Desktop/
chmod +x ~/Desktop/burpsuite-pro.desktop

````

That’s it. Double-clicking the icon (or launching from your menu) will now run Burp with the correct DPI because the Path= and cd ensure it starts in the right working directory.
