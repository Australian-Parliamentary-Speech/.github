# Overview

This project is divided into three parts: download, sgml download, and parsing. The detailed documentation is in the documentation page [here](https://australian-parliamentary-speech.github.io/House_Scraper/). 

# Windows users

All commands here work natively for Mac and Linux users.

Since this project uses bash scripts (e.g., ```./run house```), Windows users need a bash environment to run these commands. One option is to install [Git Windows](https://git-scm.com/downloads/win) to create a bash shell environment. Once installed, right click "Git Bash Here" and run bash commands there. 


# Install Julia

To run the package, Julia needs to be installed. For help see https://julialang.org/install/


# Download the XML files

Step one, in your preferred directory, for example Hansard_Run/, clone the Download repo with HTTP or SSH:
```
git clone https://github.com/Australian-Parliamentary-Speech/Download.git
```

Go into the directory:
```
cd Download
```

In the directory (in a bash environment), run:
```
./run house
```
or
```
./run senate
```

The XML files should be in the directory sitemap\_xmls\_senate or sitemap\_xmls\_house.


# Download the SGML files and convert them to XML files
Step one, in your preferred directory, for example Hansard_Run/, clone the sgml2xml repo with HTTP or SSH:
```
git clone https://github.com/Australian-Parliamentary-Speech/sgml2xml.git
```

Go into the directory
```
cd sgml2xml
```
 
In the directory (in a bash environment), run:
```
./run house
```

or 
```
./run senate
```

The XML files should be in the directory senate\_xmls or house\_xmls


# Parsing

Step one, in your preferred directory, clone this repo with HTTP or SSH:
```
git clone https://github.com/Australian-Parliamentary-Speech/House_Scraper.git
```

Go into the directory:
```
cd House_Scraper
```

You would have to copy all the downloaded XML files into Inputs/hansard/, first make the directory:

```
mkdir Inputs/hansard/<senate or house>_xmls
```

```
mv -f ../sgml2xml/<senate or house>\_xmls/* Inputs/hansard/<senate or house>_xmls
```
```
mv -f ../Download/sitemap\_xmls\_<senate or house>/* Inputs/hansard/<senate or house>_xmls
```

In the directory, run:
```
./run Inputs/hansard/<senate or house>.toml
```
The output file will be in Outputs/<Senate or House>CSV

To run different year ranges or a specific year, hansard.toml file needs to be editted.



For Windows users:

```
mkdir Inputs\hansard\<senate or house>_xmls
```

```
move /Y ..\sgml2xml\<senate or house>_xmls\* Inputs\hansard\<senate or house>_xmls\
```

```
move /Y ..\Download\sitemap_xmls_<senate or house>\* Inputs\hansard\<senate or house>_xmls\
```

In the directory (in a bash environment), run:
```
./run Inputs/hansard/<senate or house>.toml
```



