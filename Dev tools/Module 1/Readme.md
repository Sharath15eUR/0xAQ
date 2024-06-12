# Git/Vim Assignments

### Assignment 1: (Complex)
1. Commit a repository with a single file change.
   ![2 assn-1](https://github.com/Sharath15eUR/0xAQ/assets/88236255/d0afd8c7-fa43-4f9a-aa3d-986681f7f933)
Commands
```git
// files changes
git add .
git commit -m "Message"
git remote add origin <git-url>
git push origin <branch>
```
2. Create 2 new directories in local PC and clone the repository on both directories.
3. Make changes in one of the directories and commit and merge the changes.
   ![4 assn-1](https://github.com/Sharath15eUR/0xAQ/assets/88236255/06c7e752-c71a-4bcd-8089-28727d1a2b8a)
Commands
```git
//dir 1
git clone <git-url>
//repo changes
git commit -am "Message"
git push origin <branch>

//dir 2
// repo changes
git commit -am "Message"
git push origin <branch> -- fails repo not update need to pull
```

4. Parallelly make a change in the same file in another directory and when the changes are pushed, there should be merge conflict noticed which should be resolved and pushed changes again.
5. Merge the changes
   ![7 assn-1](https://github.com/Sharath15eUR/0xAQ/assets/88236255/0d77343f-37b2-4b13-81de-bcc87afd2215)
Commands
```git
git config pull.rebase false
git pull --- merge conflict
// Resolve the conflict
git commit -am "Message"
git push origin <branch>
```
#### Github repo - [Dev tools](https://github.com/0xAQ/dev-tools)

### Assignment 2: (Simple)


1. Create a story.txt file using below lines, save and quit the 
  ![1 assn 2](https://github.com/Sharath15eUR/0xAQ/assets/88236255/b3acd7ee-19ec-47c7-94a4-2b255d65a656)
2.Replace fox with wolf, save and quit the file. Open and see if the changes gets reflected.
  command
```vim
:%s/fox/wolf/g
```
  ![3 assn 2](https://github.com/Sharath15eUR/0xAQ/assets/88236255/abe1b169-8baf-41f3-92c4-a60792495bb6)
3. Search for string "field" in the file and move to next and prev occurence of the string.
![4 assn 2](https://github.com/Sharath15eUR/0xAQ/assets/88236255/85b38e2e-7a3b-4de6-959c-08d896413dc8)
4. Copy the entire line "A quick fox can outsmart a lazy dog" and paste at the end of file and save it. corrrection - wolf due to step 2
command 
```vim
/A quick wolf can outsmart a lazy dog.
yy ------ copy
G ------- end of file
p ------- paste
```
![assn 2 2](https://github.com/Sharath15eUR/0xAQ/assets/88236255/7b81002a-dccb-4bca-a5e3-1cc137723f08)
5. Replace all the vowels with letter "x" in the file.
Command
```vim
:%s/[aeiouAEIOU]/x/g
```
![assn 2 4](https://github.com/Sharath15eUR/0xAQ/assets/88236255/7c8b69a8-23f0-487b-9c2e-db2bfd52092c)

