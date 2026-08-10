# ML Learning
 
👋 **If you're reading this inside VS Code, Notepad, or any other app on your computer : stop.** Close it and instead go to your web browser (Chrome, Safari, Edge : whichever you normally use), and open this link:
 
👉 https://github.com/Ravi-Chandra2709/ML_Learning
 
This file will look much nicer there : properly formatted, with clickable links : instead of showing raw text with `#` symbols everywhere.
 
---
 
## What even is Git and GitHub? (read this first)
 
Two different things, easy to mix up:
 
- **Git** is a program on your computer that keeps track of every version of your code, like a very smart "save" button that remembers everything you've ever changed.
- **GitHub** is a website that stores a copy of your code online, so it's backed up, and so you and I can both see it and share it with each other.
Think of it like this: **Git** is like Google Docs' version history (it remembers every change). **GitHub** is like Google Drive (it's where the file actually lives online so others can see it). You'll use both together.
 
We're using them for two reasons: (1) so you always have this week's material easily, and (2) because knowing Git/GitHub is genuinely a useful real-world skill on its own : separate from ML.
 
---
 
## How each week is going to work
 
1. I add a new folder to this repo (like `week-01-linear-regression`) with a notebook and a small dataset in it.
2. You get the new folder onto your computer (exact steps below, under "Getting a week's files").
3. You open the notebook in Google Colab (you already know how to use Colab) and work through it from top to bottom.
4. If you get stuck anywhere : that's totally fine and expected. Write down (in your own notes, doesn't need to be fancy) exactly where you got confused. **Please don't Google it or ask ChatGPT/Claude to solve it for you** : the point of getting stuck is that we solve it together on the call, and that's how you actually learn it.
5. Once you finish, you upload your completed notebook to **your own** GitHub (steps below, under "Pushing your work back").
6. On our weekend call, we go through your answers together, and I introduce the next topic.
---
 
## Part 1: One-time computer setup
 
You only need to do everything in this section **once**, before Week 1. After that, you'll just repeat the "every week" steps further down.
 
### Step 1: Open a terminal (this is where you'll type commands)
 
A "terminal" (also called "command line" or on Windows, sometimes "command prompt") is just a text box where you type instructions to your computer instead of clicking buttons. It looks scary at first but you'll only ever need a handful of commands.
 
**On Windows:**
1. Press the **Windows key** (bottom-left of your keyboard, the flag icon) : just tap it once, don't hold it.
2. Type the word `terminal` : a "Terminal" app icon will show up in the search results.
3. Click it, and a black or blue window opens up. That's it : that's your terminal.
*(Alternative, older way: press **Windows key + R** together, a small box pops up, type `cmd`, press **Enter**. This opens "Command Prompt," an older-style terminal. Both work : if the "Terminal" app from step 2 exists on your PC, use that instead, it's nicer.)*
 
**On Mac:**
1. Press **Command (⌘) + Space** together : this opens something called "Spotlight Search" in the middle of your screen.
2. Type the word `terminal`.
3. Press **Enter**, or click on the "Terminal" app that shows up. A window opens with a small text prompt.
From now on, whenever this guide says "open your terminal," it means: do the steps above.
 
### Step 2: Install Git
 
**On Mac:**
1. Open your terminal (see Step 1 above).
2. Type exactly this and press **Enter**:
```
   git --version
```
3. One of two things will happen:
   - If Git is already installed, you'll see something like `git version 2.43.0` printed. You're done : skip to Step 3.
   - If it's not installed, your Mac will pop up a window asking to install "Command Line Developer Tools." Click **Install**, wait a few minutes, and you're done.
**On Windows:**
1. Open your web browser and go to: https://git-scm.com/downloads/win
2. Click the big download button : it downloads a file, click on it to run it once it's done.
3. An installer window opens. You do not need to change anything : just keep clicking the **Next** button on every screen, then **Install**, then **Finish**.
4. This also installs an app called **Git Bash**. From now on, whenever this guide says "open your terminal" on Windows, use **Git Bash** instead : open it the same way as Step 1 (Windows key → type `git bash` → click it).
**How to check it worked (both Mac and Windows):**
Open your terminal (or Git Bash on Windows) and type:
```
git --version
```
Press **Enter**. If you see a line like `git version 2.xx.x`, it worked. If you see an error like "command not found," something went wrong : bring it to our call, don't worry about fixing it alone.
 
**Video that shows this whole process, step by step, if you want to watch along:** https://www.youtube.com/watch?v=h2a3Kw-I_Ec
 
### Step 3: Tell Git who you are (one time only)
 
Git wants to know your name and email so it can label your work as yours. In your terminal, type the following : **but replace the example text with your actual name and email**:
 
```
git config --global user.name "Type Your Actual Name Here"
```
Press **Enter**. For example, if your name is Priya Sharma, you would literally type:
```
git config --global user.name "Priya Sharma"
```
 
Then do the same for your email : use the **same email address you used to sign up for GitHub**:
```
git config --global user.email "your-github-email@example.com"
```
Press **Enter**.
 
*(Not sure which email your GitHub account uses? Go to https://github.com in your browser, sign in, click your profile picture top-right → **Settings** → **Emails**, and it's listed there.)*
 
**How to check it worked:** type this in your terminal:
```
git config --global user.name
```
Press Enter : it should print your name back to you. That confirms it saved correctly.
 
### Step 4: Getting this repo onto your computer (first time only)
 
In your terminal, type each line below one at a time, pressing **Enter** after each:
 
```
cd Desktop
```
*(This moves you into your Desktop folder : "cd" means "change directory," i.e. "go to this folder." This just keeps things organized so you know where to find everything.)*
 
```
git clone https://github.com/Ravi-Chandra2709/ML_Learning.git
```
*(This downloads a full copy of this repo onto your computer, into a new folder called `ML_Learning`, placed on your Desktop.)*
 
**How to check it worked:** go look at your actual Desktop (minimize the terminal, look at your screen) : you should now see a folder called `ML_Learning` sitting there. Open it and you should see a `README.md` file and a `week-01-linear-regression` folder inside.
 
---
 
## Part 2: What you do every single week
 
### Getting a week's new files
 
Each week, I'll tell you a new folder has been added (e.g. `week-02-...`). To get it:
 
1. Open your terminal.
2. Type:
```
   cd Desktop/ML_Learning
```
   Press Enter. *(This moves you inside the ML_Learning folder you already downloaded.)*
3. Type:
```
   git pull
```
   Press Enter. *(This checks GitHub for anything new and downloads it onto your computer : "pull" means "pull down the latest updates.")*
 
**How to check it worked:** open the `ML_Learning` folder on your Desktop again : you should see the new week's folder has appeared inside it.
 
### Opening the notebook in Colab
 
1. Go to https://colab.research.google.com in your browser.
2. Click **File → Upload notebook**.
3. Navigate to `Desktop → ML_Learning → week-0N-... folder` and select the `.ipynb` file inside it. It opens in Colab.
4. You'll also need that week's dataset file(s) (the `.csv` file(s) sitting in that week's `data` folder). In Colab, click the folder icon on the left sidebar, then the upload icon, and upload the `.csv` file(s) : if the notebook expects them inside a `data` folder, first click "New folder" in that same sidebar, name it `data`, then upload the CSV into it.
5. If any of this is confusing the first time, that's completely normal : skip it and we'll do it together on the call.
### Pushing your work back (after you finish a week's notebook)
 
**First : create your own GitHub repo (only needs to be done once, before Week 1's work):**
1. Go to https://github.com in your browser and make sure you're signed in.
2. Click the **+** icon in the top-right corner → click **New repository**.
3. Under "Repository name," type something like `my-ml-learning`.
4. Leave it set to **Public**.
5. Check the box that says **Add a README file**.
6. Click the green **Create repository** button at the bottom.
7. Add me as a collaborator so I can see your work: on your new repo's page, click **Settings** (top menu) → **Collaborators** (left sidebar) → **Add people** → type in my GitHub username or email → send the invite. You only do this once.
**Then, every week, once you've finished that week's notebook in Colab:**
1. In Colab: **File → Download → Download .ipynb**. This saves the finished notebook to your computer's Downloads folder.
2. Move that downloaded file into your own repo's folder on your computer. (If you haven't cloned your own repo to your computer yet, do that first the same way as Part 1, Step 4, but using your own repo's link instead.)
3. Open your terminal, and type:
```
   cd Desktop/my-ml-learning
```
   Press Enter. *(Go into your own repo's folder : adjust the name if you called it something else.)*
```
   git add .
```
   Press Enter. *(This tells Git "get ready to save everything that changed in this folder.")*
```
   git commit -m "Week 1 completed"
```
   Press Enter. *(This actually saves that snapshot, with a short note describing it : change "Week 1" to whichever week it actually is.)*
4. **Only the very first time you push from this folder** : skip this step in later weeks:
```
   git branch -M main
```
   Press Enter. *(This makes sure your saved snapshots are on a branch named "main," which is what GitHub expects by default.)*
```
   git remote add origin PASTE-YOUR-OWN-REPO-LINK-HERE
```
   Press Enter. *(This tells Git "here's the online GitHub address where this folder's snapshots should be sent." Get your own link from your repo's page on github.com : click the green **Code** button, copy the HTTPS link, and paste it in place of `PASTE-YOUR-OWN-REPO-LINK-HERE` above. You only ever need to do this once : after this, Git remembers it.)*
5. Now upload your snapshot:
```
   git push
```
   *(If this is truly the very first push and you just added the remote in step 4, type `git push -u origin main` instead, just this one time : after that, plain `git push` works.)*
   Press Enter. *(This uploads your saved snapshot to GitHub, so it shows up online.)*
6. **How to check it worked:** go to your repo's page on github.com in your browser and refresh : your notebook file should now be visible there.
7. Message me the link to your repo (or the specific file) once it's up.
 
---
 
## Weekly folders in this repo
 
- `week-01-linear-regression/` : what data is, what ML is, classification vs regression, and your first model (linear regression)
More folders will show up here as we go, one at a time.
