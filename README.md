# Install Hexo

Install Node.js  and Git

```
#For window
Node.js https://nodejs.org/dist/v12.13.0/node-v12.13.0-x64.msi
Git https://github.com/git-for-windows/git/releases/download/v2.24.0.windows.2/Git-2.24.0.2-64-bit.exe


#For Mac
brew install node
brew install git
```

Install hexo

```shell
npm install hexo-cli -g

#For more:https://hexo.io/zh-cn/index.html
```

# Theme Usage

## Init

---
```bash
git clone https://github.com/hackeruncle/hackeruncle-hexo.git ./hackeruncle-hexo
cd hackeruncle-hexo
npm install
```

## Modify
---
Modify `_config.yml` file with your own info.
Especially the section:
### Deployment
Replace to your own repo, the name is the same as github user name!
```yml
deploy:
  type: git
  repo: git@github.com:<git user name>/<git user name>.github.io.git
  branch: master
```

### Sidebar settings
Copy your avatar image to `<root>/img/` and modify the `_config.yml`:
```yml
sidebar: true    # whether or not using Sidebar.
sidebar-about-description: "<your description>"
sidebar-avatar: img/<your avatar path>
```
and activate your personal widget you like
```yml
widgets:         # here are widget you can use, you can comment out
- featured-tags
- short-about
- recent-posts
- friends-blog
- archive
- category
```
if you want to add sidebar widget, please add at `layout/_widget`.
### Signature Setup
Copy your signature image to `<root>/img/signature` and modify the `_config.yml`:
```yml
signature: true   # show signature
signature-img: img/signature/<your-signature-ID>
```
### Go to top icon Setup
My icon is using iron man, you can change to your own icon at `css/image`.

### Post tag
You can decide to show post tags or not.
```yml
home_posts_tag: true
```

### Markdown render
My markdown render engine plugin is [hexo-renderer-markdown-it](https://github.com/celsomiranda/hexo-renderer-markdown-it).
```yml
# Markdown-it config
## Docs: https://github.com/celsomiranda/hexo-renderer-markdown-it/wiki
markdown:
  render:
    html: true
    xhtmlOut: false
    breaks: true
    linkify: true
    typographer: true
    quotes: '“”‘’'
```
and if you want to change the header anchor 'ℬ', you can go to `layout/post.ejs` to change it.
```javascript
async("https://cdn.bootcss.com/anchor-js/1.1.1/anchor.min.js",function(){
        anchors.options = {
          visible: 'hover',
          placement: 'left',
          icon: ℬ // this is the header anchor "unicode" icon
        };
```

## Hexo Basics
---
Some hexo command:
```bash
hexo new post "<post name>" # you can change post to another layout if you want
hexo clean && hexo generate # generate the static file
hexo server # run hexo in local environment
hexo deploy # hexo will push the static files automatically into the specific branch(gh-pages) of your repo!
```

Push hexo file to github:
```bash
git add .
git commit -m 'init'
git push -u origin master
```

Push hexo blog html to local : 
```bash
hexo clean && hexo g && hexo s
```
open web: [http://localhost:4000](http://localhost:4000)

Push hexo blog html to github :
```bash
hexo clean && hexo deploy
```
open web: [https://hackeruncle.github.io](https://hackeruncle.github.io)