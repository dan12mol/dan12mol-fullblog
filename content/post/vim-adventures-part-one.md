+++

author = "Dan Moldovan"
comments = true
date = "2015-08-22T09:02:35+03:00"
draft = false
image = ""
menu = ""
share = true
slug = "vim-adventures-part-one"
tags = ["vim", "web development", "tutorial"]
title = "Vim Adventures (Part 1)"

+++

---

It’s been quite a while since my last post. I’ve left off writing for what seemed to be more important at the time. Projects, life events and other things have cluttered my schedule and I’ve left writing aside which looking back might have been a mistake. Laying down my thoughts on paper (desktop) is such a relaxing motion that I should take a note to self to do it more oftenly. I’ve decided I’d lay off the background story continuation for another time and start writing about some techie stuff.

Few years ago before I had learned what the power of a text editor can be I was mostly using IDEs, which now seems pointless since they’re mostly either cluttered with things that are unnecessary or slow. I’m not looking to trash any IDE user here but my personal preference has slowly led me towards text editors. First off there was **Sublime Text** which seemed like a piece of heaven to me. It has so many features and plugins and so many ways to edit text and improved productivity that it just seemed to good to be true, and indeed I’m fairly certain that it’s the most used editor at least in the web dev community. About a year ago I stumbled upon **Atom** which is Github’s open source text editor. A quick look and I decided Sublime Text is definitely worth dumping for this. 

A few reasons why I chose Atom over Sublime Text:

- Good looking Icon
- Open-source
- Built with Web technologies (HTML, CSS, JS)
- Hackable

The **Hackable** part I discovered only a few months in using Atom and it was such a delightful surprise for me. I even started writing plugins and helpers on my own such as toggle. All in all Atom was quite a blast and I’m still using it intensively and it is my #1 recommendation as a text editor. Besides, I was a huge Github fan to begin with.

![Alt text](../images/dojocat.jpg)

 I’ve heard awesome thing about **Vim**. So I started running through the docs and **vimtutor** I decided I’m in love with it. But the problem is it took me quite a long time to learn and quite a long time to actually be able to say that I have increased productivity using Vim rather than Atom.
 
 Anywhoo, I’ll leave a basic .vimrc below with comments as to what everything does just as a started in case you we’re thinking of picking vim up. Scroll all the way down if you don’t care about explanations and just want to get the .vimrc and get down to business.
 
 ---
 
 First things first, create a .vimrc file in your home directory by running touch ~/.vimrc. The vimrc file is loaded when vim startup and has all sorts of possibly imaginable configuration in it. This is the heart and soul of you editor customisation. Next up, lets put some stuff in it. Just paste in the commands line by line if you want them enabled.
 
 `set history=200`<br>
 By default vim remembers the last 20 ex commands that you use (searches as well). This defaults that number up to 200.

`set ruler`<br>
This enables a line/character helper at the bottom of the screen letting you see which line and character you are currently on.

`set cursorline`<br>
This slightly highlight the current line as a visual helper.

`syntax on`<br>
Turns on syntax highlighting.

`filetype plugin indent on`<br>
Allows vim to auto-indent lines based on current filetype. Useful for web developers since we’re editing files with various extensions.

`set tabstop=2`<br>
`set softtabstop=2`<br>
Set tab length to 2 (replace number with 4 or whatever you like best).

`set expandtab`<br>
This converts tabs into soft tabs (spaces).

`set number`<br>
Displays all line numbers on the left-hand side of the editor.

`set wildmenu`<br>
This enables navigating between different options when using tab auto-complete.

`set lazyredraw`<br>
This enables buffering of screen updates instead of updating all the time, effectively increasing performance

`set showmatch`<br>
A must in a devs toolkit. Highlights matching paranthesis.

`set incsearch`<br>
Enables incremental search. Highlight matching real-time when searching

`set hlsearch`<br>
Will highlight all matching results of a search query.

`setnrformats=`<br>
Treats all numbers as decimal. This is to be able to effectively increment number with leading zeroes. Don’t use if you work with non-decimal numbers oftenly.

---

There’s one more thing I want to talk about before wrapping things up, which are package managers. A big part of customizing vim are the plugins which you can find online. Having a package manager that manages all your plugins and injects them into vim can be of great help. There’s a bunch of package managers out there, I personally went with **Pathogen** because it’s the first one I found and it’s great, there’s really no other reason.

Go over to [pathogen.vim](https://github.com/tpope/vim-pathogen), follow the instructions to install this great plugin and you’re ready to go. This will also add `execute pathogen#infect()` to your vimrc. There’s only 2 plugins which required extra vimrc changes and those are [Solarized](http://ethanschoonover.com/solarized), which is the colorscheme I use and I added<br>
`let g:solarized_termtrans = 1`<br>
`set background=light`<br>
`colorscheme solarized`<br>
for it. The other one is [CtrlP](https://github.com/kien/ctrlp.vim) which is a fuzzy finder plugin (kindof like Cmd+P in Sublime, Atom) and it’s great but indexes files a bit slowly so I coupled it with [Ag](https://github.com/ggreer/the_silver_searcher) to make it lightning fast, effectively adding another line to my vimrc.<br>
`let g:ctrlp_user_command = 'ag %s -l --nocolor -g ""'`

That’s basically it for my .vimrc file. Stay tuned for **Vim adventures (Part 2)** where I’ll be going over some basic vim commands and how to do various tasks in vim to ease your workflow.
’Til next time!
