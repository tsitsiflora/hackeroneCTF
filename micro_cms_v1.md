## Micro CMS v1

This is an easy challenge

### Steps to reproduce 

1. Start the challenge
2. You should see a page with 3 links, `Testing`, `Markdown Test`, `Create a new page`

### Flag 1

1. Click on create a new page
2. You should see a page where you can add a title and content, then click create
3. Analyze the new page url, you should see the indexing on the end of the page url i.e., `https://31f2d2953d58f9ac05d32e6f6953c859.ctf.hacker101.com/page/10`
4. Go to edit page and notice that pages 3 to 9 are skipped and the new page is indexed 10
5. Try all the other pages by editing the url index
6. The flag will be displayed when you reach page 7 i.e, `https://31f2d2953d58f9ac05d32e6f6953c859.ctf.hacker101.com/page/edit/7`

### Flag 2

1. Click the Testing page and go to `Edit this page`
2. The title section is vulnerable to simple XSS
3. Edit the title to <h1>Testing</h1>
4. Click `save` then `Go home`
5. The flag will be reflected on the home page as an alert

### Flag 3

1. This is a url manipulation vulnerability. Click on any page.
2. Go the the `Edit this page` page
3. Add a closing quote on the url so that the url looks something like this `https://31f2d2953d58f9ac05d32e6f6953c859.ctf.hacker101.com/page/edit/10'`
4. The flag will be revealed

### Flag 4

1. The vulnerability here is that `<script>` is is filtered but not attributed inside <>. This is again a Simple XSS. Open the `Edit Markdown` page
2. Where there is a button tag, replace it with the following: 


<button onclick="alert('xss')>Some button</button>

3. Save the page and right click to view page source
4. The flag will be revealed
