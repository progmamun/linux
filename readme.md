# Linux kernel, an operating system kernel first released on September 17, 1991, by Linus Torvalds. Linux is typically packaged in a Linux distribution.

---

- DNS google: 8.8.8.8 8.8.4.4
- $ cd ~/Downloads/
- Extract file .tar.gz ( $ tar -xzvf file_name)
- ll(folder er sob kicu dekaba)
- sudo apt-get autoremove
- sudo rm -rf /tmp/\*
- sudo apt-get update
- sudo apt-get upgrade or sudo apt-get dist-upgrade
- sudo apt-get source <package name>
- sudo apt-get purge <package name> (remove)
- sudo apt-get clean
- sudo apt install nodejs npm
- sudo apt remove nodejs npm

- NVM:

1. gitlink -cmd
2. source ~/.bashrc
3. nvm install <version-16.8.0>
   4.nvm use <version-name> change version

- ctrl+alt+t >open terminal
- ctrl+l > clear
- ctrl+d > close terminal
- Reading the Man Pages
- $ man -k which
- $ man 1 sol
- Redirection Standard Output
- $ cat
- $ cat 1> output.txt
- $ cat > output.txt (same upline)
- $ cat 1>> output.txt (over right old txt still there)

## Redirection Standard input + Standard Error

- $ cat 2> error.txt
- $ cat 2>> error.txt
- $ cat 1>> output.txt 2>> error.txt
- $ cat >> output.txt 2>>error.txt
- $ cat > input.txt
- $ cat < input.txt
- $ cat 0< input.txt 1> hello.txt (other terminal open and run $ tty)
- $ cat 0< input.txt > /dev/pts/1
  communication two terminal

## Piping

- $ date 1> date.txt
- $ cut < date.txt --delimiter " " --fields 1
- $ date | cut --delimiter " " --fiels 1
- $ date | cut > today.txt --delimiter " " --fields 1
- $ date | cut --delimiter " " > today.txt --fields 1
- $ date | cut --delimiter " " -fields 1 | command -options args
- $ date | tee fulldate.txt | cut --delimiter=" " --field=1
- $ date | tee fulldate.txt | cut --delimiter=" " --field=1 > today.txt
- $ date | tee fulldate.txt | cut --delimiter=" " --field=1 | tee today.txt
- $ date | xargs echo
- $ date | xargs echo "hello"
- $ date | cut --delimiter=" " --fields=1 | xargs echo

## Navigating the file system

- $ pwd
- $ ls
- $ ls -lh
- $ cd ~/Downloads
- $ cd Downloads
- $ cd (back home)
- $ ls -a (hidden file show)
- $ cd . (refesh)
- $ cd .. (back)
- $ cd etc

## Creating Files and Directories

- $ touch files1
- $ touch ~/Documents/distantfile
- $ echo "hello" > hello.txt
- $ mkdir -p new/thing/index
- $ mkdir happy birthday (2 folder)
- $ mkdir "happy birthday"
- $ mkdir {jan,feb,mar,apr}\_{2021,2022,2023,2024}
- $ mkdir {jan,feb,mar,apr,may,jun,jul,aug,sep,oct,nov,dec}\_{2017..2022}/file{1..100}
- $ touch file{A,B,C}.txt
- $ touch file{F..v}.txt

## Deleting Files and Folders

- $ rm deleteme
- $ touch Doucments/deleteme
- $ rm Doucuments/deleteme
- $ rm file1.txt Doucments/file2.txt Downloads/file3.txt
- $ rm \_.txt
- $ rm file\_
- $ rm _2_
- $ rm -r delfolder/
- $ rm -ri delfolder/
- $ mkdir -p delfolder/folder{1..3}
- $ touch delfolder/folder{1,2}/file{1..10}.txt
- $ rmdir delfolder/\_ (rmdir deleted empty directory)
- $ rm -r project/

## Copying Files and Folders

- $ cp file1.txt file2.txt
- $ cp file1.txt file2.txt destination/
- $ cp destination/\_ .
- $ cp destination/\_ ..
- $ cp -r copy_me/ destination/ (folder copy)

## Moving + Renaming Files and Folders

- $ mv oldname.txt newname.txt
- $ mv newfolder/\_ .
- $ mv file\* newfolder/
- $ mv newfolder/ ~/Documents/
- $ mv ~/Documtns/newfolder/ ./jackpot (~ = home folder)

## Editing Files using Nano

- ctrl+o (save) then enter
- ctrl+x (exit)
- $ sudo nano /etc/nanorc
- ^ = ctrl
- M- = alt, esc or cmd (depending on your layout).
- nano's configuration file is /etc/nanorc

## The Locate command

.conf
.log

- $ locate \*.conf
- $ locate -i \_.CONF (insensitive letter when use i)
- $ locate -i --limit 3 \_.conf
- $ locate -S (inf database)
- $ locate -S > ~/Desktop/database\*before.txt
- $ locate -e \*.conf
- $ locate --existing \_.conf (same result)
- $ locate --follow \_.conf
- $ locate --existing --follow -i --limit 5 \_.conf
- $ sudo updatedb
- $ man updatedb

## The Find command

- $ find /home/mamun/Documents/
- $ find . -maxdepth 1
- $ find . -maxdepth 2
- $ find . -maxdepth 4
- $ find . -type f
- $ find . -type d
- $ find . -maxdepth 1 -type d
- $ find . -name "5.txt"
- $ find . -maxdepth 2 -name "\_.txt"
- $ find . -maxdepth 2 -name "file?.txt"
- $ sudo find / -type f -size +100k | wc -l
- $ mkdir haystack/folder{1..500}
- $ touch haystack/folder{1..500}/file{1..100}
- $ find haystack/ -type f -name "needle.txt"
- $ find haystack/ -type f -name "needle.txt" -exec mv {} ~/Desktop \;

## Viewing Files

- $ cat file1.txt
- $ cat file[1-5].txt | tac > reversed.txt
- $ tac myfile.mp3 > myreversedfile.mp3
- $ cat file[1-5].txt
- $ cat file[1-5].txt | rev
- $ cat file[1-5].txt | tac
- $ sudo find / -maxdepth 5 -name "\_.conf" -size +20k
- $ cat /etc/cups/cups-browsed.conf
- $ tac index.txt
- $ rev index.txt
- $ cat index.txt
- $ find | head -n 5
- $ find | head -n 5 | tac
- $ cat /etc/cups-browsed.conf | wc -l
- $ head -n 20 /etc/cups/cups-browsed.conf
- $ tail -n 20 /etc/cups/cups-browsed.conf (tail- bottom)

## Sorting Data

- $ sort index.txt
- $ sort words.txt > sorted.txt
- $ sort words.txt | tac
- $ sort -r words.txt (r=reversed)
- $ sort numbers.txt | less
- $ sort -n number.txt | less
- $ sort -nr number.txt | less
- $ sort -u number0-9.txt | less
- $ sort -u number0-9.txt
- $ ls -l /etc | head -n 20 | sort -k 5n
- $ ls -l /etc | head -n 20 | sort -k 5nr
- $ ls -ln /etc | head -n 20 | sort -k 5nr
- $ ls -lh /etc | head -n 20 | sort -k 5hr (human readable)

## Searching File Content

- $ grep e hello.txt
- $ grep -ic a gadsby_manuscript.txt
- $ grep -ic e gadsby_manuscript.txt
- $ grep -i "our boys" gadsby_manusript.txt
- $ wc -l gadsby_manuscript.txt
- $ grep -v e gadsby_manuscript.txt (v= e letter bad a sob dekaba)
- $ grep -cv e gadsby_manuscript.txt (cv letter count korba)
- $ ls -lF / | grep root
- $ ls -lF / | grep opt
- $ ls -F /etc | grep -v / > files.txt
- $ ls -F /etc | grep -v / | sort -r > files.txt
- $ man -k print | grep files

## File Archiving + Compression

- $ ls -lh
- $ tar -cvf ourarchive.tar file[1-3].txt
- $ tar -tf ourarchive.tar (t-test what inside the archive file)
- $ tar -xvf ourarchive.tar (extact)
- $ gzip ourarchive.tar
- $ gunzip ourarchive.tar.gz (undo gzip)
- $ bzip2 ourarchive.tar
- $ bunzip2 ourarchive.tar
- $ zip ourthing.zip file1.txt file2.txt
- $ unzip ourthing.zip
- $ tar -cvzf ourarchive.tar.gz file[1-3].txt
- $ tar -cvjf ourarchive.tar.bz2 file[1-3].txt
- $ tar -xvzf ourarchive.tar.gz
- $ tar -xvjf ourarchive.tar.bz2

## Bash Scripts

$ nano our_script.sh
#!/bin/bash

mdir ~/Desktop/magic
cd ~/Desktop/magic
touch file{1..100}
ls -lh ~/Desktop/magic > ~/Desktop/magic.log
$ bash our_script.sh (run)
nano backup.sh
#!/bin/bash

tar -czf ~/Desktop/backup.tar.gz ~/{Documents,Downloads,Desktop,Pictures,Videos} 2>/dev/null

bash backup.sh

- chmod +x backup
  .bashrc
  PATH="$PATH:$HOME/bin"
  Scheduling With Cron
- $ crontab -e
