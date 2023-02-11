# Toriality's DevLogs

**Here I'll share all my projects' progress!**

<details>
  <summary>DevLogs Archives</summary>

- 2023
  - [January](archive/2023-01.md)
  - February (current)

</details>

## DevLog #8 - 05.02.2023

Today the site has made a lot of progress I would say.

We start with a new page created: ListMissions. As the name says, this page will show the list of missions.

Besides it there will be a small banner, indicating the page, a "Daily Picks" component and a "Pinned Projects" component. I will explain them both.

- **Daily Picks**: is a function that will be added to the site that does not currently exist on the old site. Every day a mission and a mission-pack will be chosen randomly and automatically to be the daily picks of the day. By interacting with the daily picks, the user will earn points, for example, by downloading a mission, by doing a review, among other things. The idea is to try to give opportunities to all creators equally, while moving the activity and engagement of the site, rewarding users and forming an active and loyal base. Everybody wins.
- **Pinned Projects**: These are the pinned projects, which already exist on the old site, but in a somewhat disorganized way, joining pins and normal projects in the same table. In this new design, they will be separated and compacted, but keeping a certain emphasis that they deserve.

Below are some images of this new page:

![opera_SQknBkCTbC](https://user-images.githubusercontent.com/38092988/216855833-ecc25a8e-2fd7-4a01-ae05-2330318564fd.png)

![opera_UTDf1TRnS8](https://user-images.githubusercontent.com/38092988/216855845-39c304f9-25e3-4948-befc-3194c14b5e5c.png)

Along with the creation of the page, inevitably several new reusable components were created. This is great for organized and reusable code. These include components such as stylized boxes, page selector, filter selector, and a table that shows the projects.

Also some important adjustments were made to the backend, like the project search function and pagination. And at the end of the day, I started the connection between these backend functions and the frontend of the site, but I still haven't finished applying them completely.

Tomorrow I should finish all or a large part of the page and its components.

## DevLog #7 - 04.02.2023

Finally, I'm back with the devlogs!!!

Last week I went a few days without electricity because of a truck that passed on the street and took with it some electrical wires together :)

But now the lights are back on and I have some news to show you!

### DYOM Website

I managed to finalize the look and functionality of the add missions page. There are a few visual things I intend to change in some subcomponents, but I'll leave that for later, since they are components I'll reuse in other pages, and they are minor details.

Below is a gif demonstrating the page and one of its features of uploading images:

![Code_5OynWqRNB7](https://user-images.githubusercontent.com/38092988/216808909-fe07ba48-9424-41c1-b706-9cf1306eb71b.gif)

The functions of the page are 100% connected to the database and it is then possible to add new missions through it.

## DevLog #6 - 31.01.2023

I have successfully managed the uploads to the database. Now the debug page can perfectly add missions to the database as it was intended to.

![MongoDBCompass_5ir7CJvo17](https://user-images.githubusercontent.com/38092988/215996396-3a9ab6ed-b151-463d-8456-d93bf9c76c6f.png)

I also decided how the directory structure will look like.

![Code_EGKJEW6Zac](https://user-images.githubusercontent.com/38092988/215996453-806d9602-0c6d-476c-a260-cbd9051c72a0.png)

And finally, just for testing, I made a python script to delete all the folders and files whose name does not match any ID inside the database. This is important because when a mission is deleted completely from the database, its entry there is deleted, but the files that were uploaded remain on the server, taking up important storage space. So by deleting these directories, we clean up unnecessary folders and gain more storage space.

I also made a few visual changes to the site:

![opera_g3Zk9JszCu](https://user-images.githubusercontent.com/38092988/215996497-a7502fc5-43a0-41b4-90e1-de50dc188f64.png)

Now the idea is to create an official page to add missions, with a good look and functionality for the best user experience.
