# How to host an online resume and ReadMe
## Purpose
Describing the practical steps of how to host and format a resume using Markdown,Typora,GitHub and Jekyll.
## Prerequisities
To start , you already need to have a resume written in Markdown language. If you are not familiar with Markdown and haven't yet have your resume ready in markdown, I have inculded links under _More Resource_ sections. You can go through the tutorial and make the resume in Markdown. 
## Instructions
1. **Choosing Lightweight Markup**\
 Andrew Etter in his book explained why we should use Markup language instead of XML or HTML. I will breifly point them out below:
* When we store content in XML based language, It makes it difficult for people to make contribution
* Markdown has the cleanest syntax.
* Due to Markdown's popularity there are many dedicated text editors available. 
* Lightweight markup is free and easy to make changes.

Right now we will be using the Markdown language.  In order to write the resume in Markdown we need to choose a text editor. There are many text editors available. [Typora](https://typora.io/) is a very useful one. Please visit the _more resources_ section to find out more details about it. 
Once we have the resume ready and written in Markdown language, We can move forward to the next step that is where and how to host the resume online. 

2. **Use Distributed Version Control(GitHub)**\
Andrew Etter in his book preferred distributed version control systems(DVCS) over centralized system. According to him DVCS performs better and it also lets people work offline.The author also instructed to have a file named _README.md_ in the root of the repository. The _README.md_ file should have a concise summary of what is being documented and steps on how to build the documentation locally. Additionally, It should also include steps on how to make contribution on the project or product. 

For our purpose we will use GitHhub which is also a DVCS. To start, we first need to create an user account on GitHub If we already don't have one. 

Once you are logged into your account,  Follow the following steps:
* **Create a  repository**
> 1. Click on _Repositories_
> 2. Click the green button which says _New_
> 3. name the repository as username.github.io where username is your username on GitHub . Be careful about the username since it has to match your username exactly in order to work.
> 4. Scroll down and choose _Public_
> 5. Scroll down and check off the box that says _Add a README file_ . If you are going to write the README file in a text editor and later upload to the repository, you can ignore this.
> 6. Click on _Create repository_
* **Add file to the Repository**
>1. Once you have created the repostory , you will see a quick setup screen. click on _uploading an existing file_
>2. Click on the _choose your files_ option and select both your resume and ReadMe file. Make sure the name of your resume file is named as index.md and your readme file is named as README.md
>3. click on the green button that says _Commit changes_
Now you will be able to see the files in your repository. 
* **Host online by generating Static Websites**
There are many reasons to use static website to show our resume online. Author Andrew etter mentioned some of the advantages of static website in his book _Modern technical Writing_. some of the advantages he mentioned are that the static websites are simple,portable and secured. He also added migrating the entire website is really easy too since they have no server-side application dependencies and no database. Below are the steps you can follow to generate a static website to show your resume:

>1. once you are inside the repository and can see README file, look at top left corner and Click on _Settings_.
>2. Once you are in settings look at the left side and click on _pages_
>3. Now click on the _publish page_ option. You will see a message saying _ Your site is published at https://username.github.io/
>4. Afterwards look right below where it says _Theme Chooser_ and click on _Change Theme_
>5. Now you will see some themes or templates from Jekyll that you can implement in your page. Click on one of the theme that you have choosen and then click the green button on the right hand  under the theme options that says _select theme_
>6. Now click on the link again where it says your site is published at. You will be able to see your resume with the theme you have choosen. 

Your final resume should look like the this on the website,
![Resume](https://github.com/nomanaa/nomanaa.github.io/blob/main/ResumeGIF.gif)
* **More Resources**
>1. To know details about Markdown and to learn it : [Markdown](https://www.markdowntutorial.com/)
>2. Link to Andrew Etter's book: [Modern Technical Writing](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
>3. Details about Jekyll: [Jekyll](https://jekyllrb.com/)
## Author and Acknowledgement
This article is written by Abdullah Al noman. 
Special courtesy goest to Andrew Etter's books and my COMP 3040 group member.
## FAQ
1. _Why is Markdown better than word processor_?
>Accroding to the author of Modern technical writing, Markdown is better than word processor because it does not have an instance like word processor. So none can hack it. Markdwon also does not have comment section. Hence, bots can not spam it. Markdown also never crashes.
>
2. _Why is my resume not showing up_?
>Sometimes pages takes up to 20 minutes to build and deploy. So if you do not see your resume right away, wait for more than 20 minutes and then check it. Also, make sure you are putting the correct URL with your username spelled correctly.

