## Postbook

This is an easy challenge

### Steps to reproduce

1. Start the challenge
2. You should see a page that prompts you to sign up or sign in

### Flag 1

1. Create a user using any credentials
2. When you sign in, you will see some posts that have already been published. Visit these posts and take note of the index in the url i.e., `https://4a0a223ac914b592e3b2c43e7496e9e5.ctf.hacker101.com/index.php?page=view.php&id=1`
3. Notice that there is index 1, then 3. Try replacing the index with 2.
4. You will be able to view a secret post on this page and the flag will be displayed.