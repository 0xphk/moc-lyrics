# moc-lyrics
moc-lyrics is a simple bash script that fetches the lyrics of current song playing in [MOC] (music on console) music player.

Adaptation of the original script to store the lyrics in mocp compatible format, 
so they can be displayed later in player ui using the ```'L'``` command,
without the requirement to fetch the lyrics again and thus enabling offline use.

If script is bound to one of the ```ExecCommand[1-10]``` shortcuts in the moc config file,
lyrics can be displayed, fetched and locally saved using the corresponding function ```F[1-10]``` key.

The Perl dependency was also removed and URL encoding is done using bash urlencode function.
To print the separator line, printf is used using ```tput cols``` instead of ```stty size``` and Perl.

Additional small changes to the code include change of the bash function naming convention
```function_name() {}``` instead of ```function function_name () {}```
and a few other, mostly cosmetic changes.

Removed the error reporting instructions to the original repo as well, 
as this version is heavily modified and error reports shouldn't hit the original author.
If something does not work, please open an issue on the github page.

### Dependencies :
- Wget - [Wget] is a free software package for retrieving files using HTTP, HTTPS and FTP, the most widely-used Internet
protocols. Most Linux distributions have Wget in their package repositories so you can easily install Wget via the package manager of your distribution in case it is not installed on your system.


### Installation :
User installation without ```sudo``` requirement

Using git:

```
git clone https://github.com/0xphk/moc-lyrics.git
```

Set executable bit and copy the script to your preferred users bin directory, which also should be listed in users ```$PATH``` variable.


```sh
cd moc-lyrics
chmod u+x moc-lyrics
cp moc-lyrics ~/bin/
```
Adding to moc config:

(assumes ExecCommand1 isn't set, otherwise change to the free ExecCommand, or edit config directly)

```sh
sed -i 's|#ExecCommand1 =|ExecCommand1 = ~/bin/moc-lyrics|' ~/.moc/config
```

If moc is running, detach mocp using ```q``` and start it again


### Usage :
Press the corresponding function key, ```F1``` in above example

moc will display lyrics if found and save it as moc compatible lyric file alongside the currently played song.

Can be run in terminal as well, like the original version of the script.


### Support :

If you like **moc-lyrics**, please consider supporting the original author!

[![Support via PayPal](https://cdn.jsdelivr.net/gh/twolfson/paypal-github-button@1.0.0/dist/button.svg)](https://paypal.me/hakerdefo)  
[!["Buy Me A Coffee"](https://user-images.githubusercontent.com/1376749/120938564-50c59780-c6e1-11eb-814f-22a0399623c5.png)](https://www.buymeacoffee.com/hakerdefo)  
[![Support via Liberapay](https://liberapay.com/assets/widgets/donate.svg)](https://liberapay.com/hakerdefo/donate)  


### Credits :
[hakerdefo] - for the original version of the script

[Federico Builes] - moc-lyrics wouldn't have been possible without wonderful [makeitpersonal] created by Federico.


### License :
[![Public Domain Mark](http://i.creativecommons.org/p/mark/1.0/88x31.png)](http://creativecommons.org/publicdomain/mark/1.0/)  
This work (<span property="dct:title">moc-lyrics</span>, by [<span property="dct:title">hakerdefo</span>](https://github.com/hakerdefo/moc-lyrics)), identified by [<span property="dct:title">hakerdefo</span>](https://hakerdefo.blogspot.com), is free of known copyright restrictions.

[Wget]:https://www.gnu.org/software/wget/
[hakerdefo]:https://github.com/hakerdefo/moc-lyrics
[moc-lyrics]:https://github.com/hakerdefo/moc-lyrics
[MOC]:http://moc.daper.net
[Federico Builes]:https://github.com/febuiles
[makeitpersonal]:https://github.com/febuiles/makeitpersonal
