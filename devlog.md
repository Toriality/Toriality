# Toriality's DevLogs

**Here I'll share all my projects' progress!**

## DevLog #2 - 26.01.2023

While taking a short break from DYOM Webiste, I decided to make some major changes to DYOM Bingo.

This morning at 9:00 AM I started thinking about some ideas that would be interesting for the new version of the bingo. And I came up with these ideas:

- Filters/limits: so that users who don't have certain features of newer versions of Rainbomizer can still be entertained with the bingo. For example, to mark certain slots it was necessary to have the auto-translate feature of Rainbomizer, but not all users have this version, so the filter to remove slots that need auto-translate was created
- A button to generate slots: a simple button that regenerates new slots, instead of having to reload the page
- Tooltips: some of the slots might not be very clear to understand, so when you hover the mouse over them, there will be tooltips explaining what the slot is about. This was also nice to write some interesting trivia about DYOM
- New theme: total reconstruction of the theme, with new colors and images, leaving aside that boring black and white visual that looked like a pure HTML page

All these ideas were successfully developed by the end of this afternoon. The final result? This one:

![image](https://user-images.githubusercontent.com/38092988/215221056-6707a58a-2e3a-45e4-a60f-b868afe97add.png)

After showing the site on the GTA Rainbomizer Discord, some users pointed out that the limit buttons were not working. Actually, what was happening was that the :has CSS was not compatible with the Firefox browser, and so when the user clicked on the filter button, there was no visual indication that it was active/deactivated.

I was able to replace the CSS :has with a slightly larger code within JavaScript, but it works just the same. The error apparently no longer occurs.

```css
.formdiv label {
  text-align: center;
  width: 100%;
  border-radius: 8px;
  padding: 16px 8px;
  background-color: #eee;
  border: 0.6rem solid #ccc;
}
.formdiv label:has(input:checked) {
  background-color: rgba(255, 204, 204, 0.75);
  border-color: rgba(255, 49, 49, 0.75);
}
.formdiv label:hover {
  background-color: #ffffcf;
  border-color: #ffdf70;
}
```

That's the CSS code that got replaced by this Javascript code:

```javascript
// :has alternative for Firefox
let formLabels = document.querySelectorAll(".formdiv label");
let checkboxes = document.querySelectorAll("input");
checkboxes.forEach((input) => {
  input.addEventListener("change", () => {
    let parent = input.parentElement;
    if (input.checked) {
      parent.style.backgroundColor = "rgba(255, 204, 204, 0.75)";
      parent.style.borderColor = "rgba(255, 49, 49, 0.75)";
    } else {
      parent.style.backgroundColor = "#eee";
      parent.style.borderColor = "#ccc";
    }
    parent.addEventListener("mouseenter", () => {
      if (!input.checked) {
        parent.style.backgroundColor = "#ffffcf";
        parent.style.borderColor = "#ffdf70";
      }
    });
    parent.addEventListener("mouseleave", () => {
      if (!input.checked) {
        parent.style.backgroundColor = "#eee";
        parent.style.borderColor = "#ccc";
      }
    });
  });
});
```

At the end of the day I got a big surprise.

[My post on the DYOM Twitter account](https://twitter.com/OfficialDYOM/status/1618686351842607104) about this new version of DYOM Bingo was noticed by streamer Joshimuz, who retweeted it.

Besides being a big admiration for me, [Joshimuz](https://www.twitch.tv/joshimuz) is a popular streamer and his retweet caused the post to get more than 3 thousand views and dozens of likes. Definitely something that made me very happy and proud of this modest little job for the DYOM community :) .

## DevLog #1 - 25.01.2023

Today is the first day writing a devlog so I think it's important to give some context.

At the moment I am working on a project in which I aim to rebuild the DYOM website (https://dyom.gtagames.nl/) from scratch.

I am using HTML, CSS, JavaScript, React, MongoDB, among other technologies for this project. If you want to contribute the code will always be open-source and the repository link is here: https://github.com/Toriality/DYOM-Website

Let's get started...

### 1. The beginning: 

The project started one day ago. At the end of that day the site had a (fairly) functional backend, and a very simple frontend full of improvements to make. Here's the result: 

![dyom1](https://user-images.githubusercontent.com/38092988/214803680-fd3038da-61fe-445a-a5a8-9fa5a9778c12.png)

It is worth mentioning that the design of the project is based on a project I did at Figma that also rebuilt the DYOM site from scratch, but only visually. Link below:

https://www.figma.com/file/JoQWxWZ3WEO6YtLCOLtbMG/DYOM?node-id=0%3A1

### 2. Building the homepage: 

Today my focus was to start working on the homepage. Starting from the beginning, I tried to make the DYOM banner - the first thing a visitor to the site will see, so it should be pretty, eye-catching and straight to the point.

![dyom2](https://user-images.githubusercontent.com/38092988/214803857-8b916b7a-889b-4947-bab0-8914e837401d.png)

Credits to Zeko, designer of the missionpack [Katabasis](https://gtaforums.com/topic/964193-mp-katabasis/), for the banner picture.

### 3. RTK Query: 

I was able to implement some authentication features using Redux-Toolkit. Currently there are functions to register a new user and login. It's in a very simple stage and far away from the structure I want to achieve in the final result, but it's good for now.
