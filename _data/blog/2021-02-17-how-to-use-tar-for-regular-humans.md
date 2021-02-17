---
template: BlogPost
path: /tar-for-humans
date: 2021-02-17T03:37:15.620Z
title: How to use tar for regular humans
thumbnail: /assets/tar.png
---
Tar is a powerful command-line tool. I was setting up some Jenkins job and wanted to create an artifact to use with another pipeline. I first needed to zip up a directory and then unzip the artifact. Looking at tar commands they look a bit intimidating `-xvf`. what are those flags?  I'm a big fan of long-from flags so here is how you tar a directory and how you unzip it. 
zip it: 

```
tar --gzip --create --file name.tar.gz --directory ./path/to/directory .
```

Short form: 

```
tar -zcf name.tar.gz --directory ./path/to/directory .
```

Now that a tar file, you can untar it by: 

```
tar --extract --file name.tar.gz --directory ./path/to/directory
```

Short form: 

```
tar -xf name.tar.gz -C ./path/to/directory
```

You need to make sure the directory exists if you are extracting it into one. 

🤫 Here is a little secret. use man to understand command flags. Try man tar and see the explanation for each flag.
