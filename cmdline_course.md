---
layout: default
---
# Command line tools for linguists

The command line tools for linguists course provides a look into file parsing using a UNIX system. It has useful commands for creating different types of data files from text files, for example word frequency lists for corpus processing. For Windows users like myself the differences between the systems weren't insurmountable, and I actually grew to like the UNIX system. The only issue is the remote computer I had to use due to my Win 8, but that's hardly Linus's fault :) 

<img src="assets/images/git_commit_2x-2.png" alt="Frustration overload" hspace="20" width="30%" align="right"/>

Every week we were treated to a short comic strip detailing the intricacies of UNIX systems, but during the last week I definitely felt like this... 



## Week 1

The first week was introductory, and most of my time that week was spent trying to install Linux on my near-obsolete Windows 8. Don't recommend it. Some commands were learned, however, and among these are the ever useful folder and file creation commands _mkdir_ and _touch_. 

## Week 2

On the second week, we were ecouraged to navigate our newly installed UNIX system. We continued with some file and folder handling such as moving and deleting files, but also added some user-right-manipulation into the mix. The _chmod_ command was a tricky one to figure out by the numbering system, but luckily you can also add (+) executable (x) rights for the user (u) by using letters:

$ chmod u+x "target_file"

## Week 3

On week 3 we tried some corpus processing, and there were quite a few things  we did to some poor text files. The list is quite long, but here are a few examples:
* convert Windows text files into UNIX text files and vice versa 
* sort the lines in a file into alphabetical and numerical order by using the _sort_ command
* find all lines in a text file which start with an upper case character 
* search for patterns in files using grep (i.e. regular expressions) 

## Week 4

This week we continued with more advanced corpus processing, moving onto using the _sed_ command. Regular expressions can also be used with sed, for example to find a replace parts of text. Let's say you want to replace the word x with y in a text you wrote because it just sounds better. You can use sed for that: 

$ sed 's/x/y/'

The letter 's' before x stands for 'substitute'.

## Week 5

Week 5 was about scripting and configuration files. I'm not a fan of the fiddly stuff, but scripting is always a treat. The only downside to it is trying to figure out the new syntax, and not repeat what you already know and assume it works. One task this week was to create a script that compares two files and outputs the result as either 0 or 1. Here's my short loop:

    #!/bin/bash

     diff $1 $2 > /dev/null
    if [ $? == 1 ]
    then
        echo -e "1\n"
    else
        echo -e "0\n"
    fi

## Week 6

On week 6 six we modified a make file in order to extract the data from several text files into one. Here's an example of code that in a MakeFile takes a script file _sent_per_line.sh_ from the src folder, and sends the result to target results/%.sent.txt using as dependency files all the files that end with .no_md.txt in the data folder.

    results/%.sent.txt: data/%.no_md.txt
        src/sent_per_line.sh $< $@

## Week 7

On week 7 we worked with Git repositories. The task was to modify files locally and then push the changes to the remote GitHub repository. Here are a few of the commands used, and I now wish that I had made a checklist like this during the week, because I kept forgetting a step before pushing the changes... :D

Command | Explanation
---	| ---
git add	| Adds modified files to staging area
git status	| Displays the status of the staging area
git commit	| Commits changes to local branch
git push	| Pushes the commits to the remote branch

## Final assignment

The final assignment doesn't seem too difficult. I ran into some zlib issues when installing ruby, but luckily Google provided the help needed. The most time consuming part is definitely the recapping of the course, but it is a good reminder of each week! 




