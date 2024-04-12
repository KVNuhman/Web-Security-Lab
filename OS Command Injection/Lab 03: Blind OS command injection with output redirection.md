# Blind OS command injection with output redirection

## Lab Description
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/b21a7718-56b5-4f94-88cf-6ad3ac12c4ca)


## Solution



We inject the payload `||whoami>/var/www/images/output.txt||` in the email field of the submit feedback section. The payload executes `whoami` command and redirects it's output to `/var/www/images/whoami.txt`.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/f1a178d2-77d4-406d-96c2-c73122398d7e)

The files created previosuly can be opened by retreiving and image and modifying the filename parameter to `whoami.txt`. We see that `peter-zQWbwc` is the user.
![image](https://github.com/KVNuhman/Web-Security-Lab/assets/46161259/86434cc2-d73b-4299-9fad-a25e2ce37958)
