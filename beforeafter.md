---
layout: page
title: Sample Editing Process
permalink: /before-after/
---
## How Do I Look?
Picture this, your friend (we'll call them Jordan) is preparing to go to a private networking event downtown. Jordan is hoping to secure an investor for their firm and has enlisted your help to ensure that the outfit they choose is appropriate. After putting on the selected piece, they spin around slowly - offering you a chance to see any imperfections or flaws in the outfit before you draw a conclusion. In the end, you suggest that Jordan switch out the blue shoes for black ones and remove the blazer. 

This same approach is how I go about editing. Upon recieving a piece of writing, I try to envision the author as my friend asking about their wardrobe choices. This helps me put the author's vision first and center any additions, withdrawals, and changes around their voice. Follow along with me as I walk you through my process for transforming an unimaginitive list of thoughts into a well dressed blog post. 

## Dressing Up For Docker
Please note that this is a sample I have created based on similar pieces I have worked on.
All edits have been created using *Bear*, a plain text editor. 

![Docker Image](/assets/images/dockersample.jpeg) 

#### This is our starting point.  
>

### Initial Thoughts
At first read, I am delighted to see that the author has well defined categories of points and that each of the bullets are complete thoughts. Since I know that this post will be part of an educational blog for new hires at the company, I also have enough information to form an angle.  

From here, I can start to focus in on the structure of the post.  

### Creating Order
We know that this blog is being used for onboarding purposes, which means that the *Get Started and Tutorials* section should be moved to the top, followed by *What is the Docker Engine*. This places *What is a Container?* at the end of the document, since it is repeating information and may be deleted later on. The reference section will be placed to the side for the time being. 

![Edit One](assets/images/Edit1.jpeg)
#### This is our first edit.
> 

### Building Structure
Now that the text is in easily identifiable chunks, it is time to zone in on the individual sections and start to create a more meaningful structure. Currently, each heading has its own sub-heading. Unfortunately, the subheadings are not generating any support for the main headings and as such, should be removed.

Next, let's take a look at the links at the top of each category. Although it will be necessary for the reader to follow these links, there is no real context surrounding them. For now, we will move the links out of the main body of text and into the references section that has been set aside - making sure to note which section each link belonged to. 

As this is meant to be blog post for new hires to follow along with (as opposed to a checklist), we will also remove the bullet point lists. 

![Edit Two](assets/images/edit2.jpeg)
#### This is our second edit.
>

### Creating Paragraphs
Wow! Even without editing the actual content, the piece already looks more put together. Now that we have a clear structure in place, we can start moving the individual sentences into a paragraph format within each section. This is also where we will highlight the angle of the piece. At the moment, I am not concerned with how the sentences or paragraphs flow together. I will address that shortly. 

I believe that the first point in the *Getting Started and Tutorials* section would make a great lead so I am going to highlight it for easy reference at a later step in my editing process. 

After moving individual sentences around a bit and selecting the lead, we can do another read through and take note of what me might think of for the content edit. I will be adding a "to-do" flag and a note after any areas I would like to revist. 

It looks a bit messy, but fear not! The next step in the process is where all the heavy editing takes place and where we can start to create a bit more *flow*. 

![Edit Three](assets/images/edit3.jpeg)
#### This is our third edit. 
> 

### Increasing Readability
For this part of the process, I will be reading through the entire post and adding in transitions, intros, and the references we removed earlier on. If I notice that something could be added, I will add it in as a suggestion to the author. 

![Edit Four](assets/images/edit4.jpeg)
> 
#### This is our fourth edit.

### Copy Edit
It has come time to do another read through - from beginning to end. This time, I am checking for inconsistencies, unnecessary repetition, punctuation, and grammar. This is the final edit before sending the annotated version to the author for review. 

![Copy Edit 1](assets/images/copyedit1-two.jpeg)
![Copy Edit 2](assets/images/copyedit2-two.jpeg)

### Final Touches

At this point in the process, I am just adding in anything the author (in this case, myself) has come back to me with. 
Below, you will find the finished blog post in its entirety. 

---  

![](DockerBlob/dockerlogoblog.png)

# Getting Started With Docker 
## Setup
As a large multi-team company, it is important for each engineer to be able to develop and collaborate with other teams efficiently. Through Docker, it is possible to have a single environment for development, testing, and production. This allows containerized applications to be easily moved from development on to higher environments without worrying about compatibility issues with other systems. In other words, Docker allows teams to fix problems without taking an entire server down - just remove the container, fix the issue, and return.

With a little setup, you will be able to use Docker to make faster updates and catch issues sooner. 

>  To set up Docker on your computer, visit [Getting Started With Docker]( https://www.docker.com/get-started)  

>  If your computer doesn’t already have Docker installed, navigate to [Docker Desktop](https://www.docker.com/products/docker-desktop) and select *download for Mac* . Follow the steps in the installation guide that pops up.   

![](DockerBlob/dockerdesktop.jpeg)


## Docker System Basics
The main Docker components are engines and containers.

If you are not sure what a container or Docker Engine is, please read through these guides prior to continuing. 
[What is a Container?](https://www.docker.com/resources/what-container)
[What is Docker Engine?](https://www.docker.com/products/container-runtime)

Docker Engines form the base of the system and run on Linux machines, whereas Docker containers provide an extra layer of security (even between containers hosted on the same engine). The containers are created on and run by these engines; each container holds all parts of a single application. Containers can be totally isolated or configured to communicate with other containers on the same or different engines. 

![](DockerBlob/engine-components-flow.png)
##### https://docs.docker.com/engine/images/engine-components-flow.png

Docker containers have the ability to support any language and a variety of platforms. Because each container is independent, any number can be placed on a single server. As applications are created and expanded, containers are easily moved to other servers with minimal interruption. 

## Recommended Learning
If you are looking for more advanced training with Docker, check out the resources below. 

#### Docker Blog
The official blog for Docker provides endless articles covering everything from developing with Docker to latest updates and news. 
An article that we recommend starting with is [API Server For Docker Infrastructure](https://www.docker.com/blog/api-server-for-docker-infrastructure/)
Navigate to [Docker Blog](https://www.docker.com/blog/) to learn more  

#### Docker Playground 
This resource requires no downloading or prior experience with Docker. 
Use Docker Playground to practice running Docker commands in a Linux terminal.

Navigate to [Learn Docker](https://www.docker.com/101-tutorial) and follow the steps under *Play With Docker*

![](DockerBlob/dockerplayground.jpeg)




