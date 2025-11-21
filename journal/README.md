# When Git Gets Messy: My First Time Using LazyGit

**By Ilayda Turgut | November 11, 2025**

---

## The Setup: A Git Nightmare

It was late on a Tuesday night, and I was staring at my terminal like it had personally betrayed me. I'd been working on a group project for my software engineering class, and somehow I'd created this absolute mess of uncommitted changes. Like, 15 files were modified, and I honestly couldn't remember what half of them were for anymore. Some changes I needed to keep, others were just failed experiments that needed to go, and my usual routine of typing `git status`, `git add`, and `git commit` felt completely overwhelming.

My goal was simple enough: commit my database changes separately from my UI updates, throw away some code that didn't work, and push everything to GitHub before our team meeting in the morning. But trying to do this through the command line felt like untangling headphones that have been in your pocket for a week.

That's when my friend walked by, saw me struggling, and said, "Dude, why don't you just use LazyGit?"

![LazyGit main interface showing file changes](/assets/lazygit-main.png)
*The LazyGit interface displaying my messy list of modified files*

## The Experience: Wait, This is Actually Cool

I had no idea what LazyGit was, but I was desperate, so I installed it with `brew install lazygit` and typed `lazygit` in my project folder. What popped up was nothing like I expected.

Instead of the usual blank terminal waiting for me to type commands, I was looking at this whole visual interface split into different sections. The left side had my files, the middle showed what I'd actually changed in the code, and the bottom had a menu showing keyboard shortcuts. Turns out this is called a **TUI** (Text User Interface), basically a program that runs in your terminal but looks more like an app with menus and stuff, instead of just a blinking cursor.

The coolest thing was how obvious everything was. This is what we learned about in class as **affordance**, basically, **affordance** means the design of something shows you how to use it, like how a door handle tells you whether to push or pull. LazyGit had this everywhere: highlighted items that clearly looked clickable, panels with borders showing they were separate sections, and that bottom menu literally telling me what keys to press. It was such a relief compared to the regular command line where I have to remember every single command or Google it for the hundredth time.

![Staging files in LazyGit](/assets/lazygit-staging.png)
*Using the spacebar to stage individual files the green highlight shows what's selected*

## The Interaction: Actually Figuring It Out

So I started just messing around with it. I pressed the arrow keys and watched the selection move between files. Then I hit `space` and boom! a file jumped from "Unstaged" to "Staged." This is what we call **feedback** in UX, basically, **feedback** is when a system shows you that it heard what you did and what happened because of it. The file literally moved and changed color right in front of me. With regular Git commands, I'd have to type `git status` again just to check if anything actually happened.

But here's where it got really cool. I needed to stage only *part* of one file-like, I wanted to commit the database stuff but not the random debug print statements I'd thrown in there. Normally I'd have to use `git add -p` which is super confusing and annoying. In LazyGit, I just pressed `enter` on the file to see what changed, then pressed `a` to get into "patch mode." 

This is where LazyGit's **mental model** just clicked for me. A **mental model** is basically how you think something works in your head like the picture you have of how a system operates. When I think about Git, I picture files and chunks of code as actual things I can pick up and move around. The command line makes me translate all that visual thinking into typed commands, which feels weird. But LazyGit just let me work the way I was already thinking about it. I could literally see each chunk of my changes in different colors and press `space` on just the parts I wanted. It felt natural.

![Partial staging in LazyGit](/assets/lazygit-patch.png)
*Staging individual chunks of code within a single file*

## The Outcome: Fast But Not Perfect

In like 15 minutes, I had everything sorted into three clean commits with actual descriptive messages. Something that would've taken me 30-40 minutes of carefully typing commands (and probably messing up and having to use `git reset` at least once) was done way faster.

But it wasn't perfect. The biggest problem was **discoverability** which is basically how easy it is to find features you don't even know exist. The bottom menu showed me some shortcuts, but there were tons of other powerful features hiding behind random key combinations that I only found when I pressed `?` to open the help menu. Like, I had no idea I could press `c` to commit, `P` to push, or `u` to undo staging until I went looking for them. The interface kind of assumed I'd either experiment with every key or read the documentation, which, let's be honest, nobody does until they're stuck.

## Reflection: What Worked and What Didn't

**What I Loved:**
- **Strong visual affordances** made it super easy to figure out what to do
- **Immediate feedback** meant I always knew if something worked
- **Mental model alignment** it matched how I already think about Git in my head
- **Reduced cognitive load** because it showed me options instead of making me memorize commands

**What Could Be Better:**
- **Limited discoverability** of the cool advanced features unless you dig into the help menu
- **Learning curve** for all the keyboard shortcuts, especially if you're used to clicking things with a mouse
- **No tooltips or progressive disclosure** to help you learn as you go

**How They Could Fix It:**

1. **Add contextual hints**: Show little tooltips when you select something, like "Press 'space' to stage" when you're on a file. Just small hints so you're not totally guessing.

2. **Progressive disclosure**: Maybe have a quick tutorial the first time you open it? Just walk through staging, committing, and pushing. People who already know it can skip it, but it would help newbies like me figure things out faster.

3. **Visual indicators for hidden features**: Put little icons or something to show when there are more options available, like how apps use those "..." menus. That way you know to look for more features instead of assuming what you see is all there is.

Even with these issues, LazyGit completely changed how I feel about using Git. It went from being this stressful thing I had to do to actually being kind of satisfying. It's a really good example of how smart UX design can make complicated tools way more accessible without making them less powerful.

---

*Tools used: LazyGit 0.55.1, Terminal on macOS*
