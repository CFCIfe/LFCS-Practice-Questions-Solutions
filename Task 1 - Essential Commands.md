### Essential Commands

Open the file under
/home/student/textreferences/editme.txt and
complete the following tasks:
1. Move line 7777 to line 1.
2. Remove line 7000.
3. Replace every occurrence of the word Earth shown with an uppercase E, with the word Globe.
4. Add a new line at the very end of the document that contains Auctores Varii.

#### Answers

1.  ```printf %s\\n 7777m0 w q | ed -s /home/student/textreferences/editme.txt```

Where:
```
printf  # for formatting and printing data
%s\\n   # Placeholder for strings with newline
m       # command that moves the line
w       #  write changes to file
q       #  quit editor
ed -s   # 'quiet' text editor.
```
2. ```sed -i '/7000/d' /home/student/textreferences/editme.txt```
3. ```sed -i 's/Earth/Globe/g' /home/student/textreferences/editme.txt```
4.  ```echo Auctores Varii >> /home/student/textreferences/editme.txt```