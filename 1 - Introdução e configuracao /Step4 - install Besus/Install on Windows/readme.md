On Windows, you need to:

Have a 64-bit version of Windows installed (Besu is currently supported only on 64-bit versions of Windows).
Download a 64-bit version of JDK/JRE. We recommend that you also remove any 32-bit JDK/JRE installations.
Download Git for Windows if you do not already have it installed.
To run gradlew, you must have the JAVA_HOME system variable set to the Java installation directory. For example: JAVA_HOME = C:\Program Files\Java\jdk1.8.0_181.
Useful commands:

Install Besu
git clone --recursive https://github.com/hyperledger/besu
Build Besu
JAVA_HOME = C:\Program Files\Java\jdk1.8.0_181.
cd besu
.\gradlew build -x test
cd build\distributions
tar -xzf besu-<version>.tar.gz
cd besu-<version>
 

Replace the <version> with the version of Besu that you have downloaded.

 

Confirm Installation
bin\besu --help