## Postbook

This is an easy challenge. This flags are not in any order, just the order I found them.

### Steps to reproduce

1. Start the challenge
2. You should see a page that prompts you to sign up or sign in

### Flag 0

1. Create a user using any credentials
2. When you sign in, you will see some posts that have already been published. Visit these posts and take note of the index in the url i.e., `https://4a0a223ac914b592e3b2c43e7496e9e5.ctf.hacker101.com/index.php?page=view.php&id=1`
3. Notice that there is index 1, then 3. Try replacing the index with 2.
4. You will be able to view a secret post on this page and the flag will be displayed.

### Flag 1

1. `User` is a common username and on this application there is a user called `User` which has a really easy password *hint
2. I used Intruder in BurpSuite to find the password
3. When you login you will see a flag.

### Flag 2

1. On your own profile, go on the page to create a post
2. Right click to `Inspect Elements`
3. You will see a hidden element with a `user-id`
4. Change the user id to 1 for the admin and your page will be reavealed

### Flag 3

1. There is a hint for this flag written `18*5`
2. The product is 945, and you can change the ID in the previous flag to 945
3. The flag will be revealed

### Flag 4

1. This flag is found on the editing page. Click on your own post and click edit
2. Right click on that page and click on `Inspect Element`
3. You will see an element like this
```
<form method="post" action="index.php?page=edit.php&amp;id=3">
 ```
You can edit the id on this element to another user's and you will see a flag there

### Flag 5


