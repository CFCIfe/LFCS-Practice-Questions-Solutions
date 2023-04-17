### Essential Commands
Open the file under
/home/student/textreferences/editme.txt and
complete the following tasks:
1. Move line 7777 to line 1.
2. Remove line 7000.
3. Replace every occurrence of the word Earth shown with an uppercase E, with the word Globe.
4. Add a new line at the very end of the document that contains Auctores Varii.

#### Answers

1.  ```
    nano /home/student/textreferences/editme.txt 
    ctrl+_ ; type 7777
    ctrl+k ; ctrl+_ ; type 1
    ctrl+U
    ```
2. ```ctrl+_ ; ctrl+k;```
3. ```sed -i 's/Earth/Globe/g' /home/student/textreferences/editme.txt```
4.  ```echo Auctores Varii >> /home/student/textreferences/editme.txt```