# VNKernel32Fix
This repository has been created to preserve the work that sweetie made in order run games such as My Girlfriend is the President and With on the Holy Night to run on Windows 8 and above.

# Installation Instructions

## Windows
Under the release section simply extract the .zip folder and place the `.dll`, `.lib`, `.def`, and `.exp` into the game's executable folder. 

For example, My Girlfriend is the President is installed by default in: `C:/Users/<user>/AppData/Roaming/ALCOT`. Place these four files next to `osana.exe`. The program should launch natively. 

## Steamdeck Instructions
Under the release section simply extract the .zip folder and place the `.dll`, `.lib`, `.def`, and `.exp` into the game's executable folder. 

If you used Steam's Proton to use Jast's installer to install the game it will be a bit complicated to find. However, it can usually be found in:

```
/home/.local/share/Steam/steamapps/compatdata/<some folder with lots of numbers>/pfx/drive_c/Users/<steam? steamdeck? (doing this from memory)>/AppData/Roaming/ALCOT
```

Hint: Once you find the executable name, `osana.exe`, right click on it and select `Copy Location`.

Once those are in place you will need to go back into Steam and go into Games -> Add a Non-Steam Game to My Library. Paste the location that you copied into the search bar and then add `osana.exe` to your library. 

To launch the game you will need to open up Properties for `osana.exe`. Under Launch Options, type or paste the following into the box:

```
WINEDLLOVERRIDES="version.dll=n,b" %command%
```

You should be able to launch `osana.exe` from your Steam Client now. 

# How to build manually

I am assuming if you are building the software manually you have some competency in terminal navigation and coding.

This can only be built on Windows since it has a dependency on Windows headers.

You will need a CMake Version greater than 3.19. [Link here](https://cmake.org/download/).
A valid installation of Visual Studio with C++ Tools. [Visual Studio Community is available for free here](https://visualstudio.microsoft.com/vs/community/).
Git to Clone the repository [Git for Windows](https://git-scm.com/download/win).

Open a terminal and clone the repository to a location of your choosing.

Create a build folder, change directories inside of it, and run the following: 

```
cmake .. -A Win32
```

Once CMake has finished generating the solution open up `version.sln` in your build folder and you are ready to program.

To build, either run `cmake --build . --config Release` from the command line or build from the Visual Studio IDE.

# Known Issues

For some reason you cannot run My Girlfriend is the President in full screen mode in Windows. So be cautious of trying to run the game in full screen. 


## Original Readme from sweetie, translated using deepl.

Program name: Win8WOH

Usage：Play Wizard's Night on Windows 8 64bit

Usage:
Put version.dll into the "WITCH ON THE HOLY NIGHT" folder.
Run "WITCH ON THE HOLY NIGHT.exe

Install:
Just extract the zip

Uninstall:
No registry or temporary files are modified.
Simply delete the entire folder to get rid of it.

Q&A
  Q:What about Windows 8 32bit?
  A:It probably works without anything.


Author：sweetie
E-mail address: bnryxx332a@mail.goo.ne.jp

Translated with DeepL.com (free version)