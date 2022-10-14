---
    layout : single
    title : "How to commit your code in your Git?"
    categories: Git
    tag: [Git, Node js]
---
#### I studyed about "things I should know when commiting node js on my gitub". I summerize here what I learned not to forget and to remind!

### Not to commit node_module files.
 You should be careful not to commit and push node modules on your git hub! it's too many!

 > ![](/images/2022-10-14-13-19-26.png)
 Look at this! Too many files. They could cause waste the memory in your git hub!! <b>YOU HAVE TO COMMIT WITHOUT LIVRARIES CUZ THEY WILL BE INSTALLED AUTOMATICALLY WHEN YOU CLONE THE REPO BY <i>pakage.json</i>!!</b>


### Use ".gitignore".
git doesn't push things written in ".gitignore" so you should write down what you don't want to commit.
>  ![](/images/2022-10-14-13-36-10.png)
> * before add "node_modules" in ".gitignore".

>  ![](/images/2022-10-14-13-40-25.png)
> write it down and save!


  

