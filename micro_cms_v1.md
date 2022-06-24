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