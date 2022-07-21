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

1. We can get this flag by manipulating the session cookies being used on the platform. You can use an extension on your browser to manage the cookies
2. Login as a normal user and take a look at your cookie. It is an md5 hash of your user ID
3. You can use an online decryptor to check and decrypt the md5 hash. This also means you can create an md5 hash of the user admin by encrypting 1
4. When you get the hash, edit the cookie value and replace it with this one. You will be able to switch accounts
5. Your flag will be revealed

### Flag 6

1. We can find this flag by deleting someone else's post by manipulating the value on the delete url
2. Login as a normal user and create a post. On that post you can see you will be able to delete or edit that post. Those options are not available for posts made by other users
3. Note down the id on the post you want to delete(it's a number)
4. Right click to `inspect elements`. You will see on your post an element like this

```
<a style="color: red;" href="index.php?page=delete.php&amp;id=8f14e45fceea167a5a36dedd4bea2543">delete</a>
```
The id is an md5 hash. If you decrypt it, you get the post id

5. To exploit this, you need to md5 encrypt the id of the post you want to delete and replace it with the one on the above url
6. Press `Delete` and you will be able to delete another user's post. Your flag will be revealed then

## Vulnerabilities Covered

1. Insecure Direct Object Reference
2. Cookie Manipulation
3. Password Attack


