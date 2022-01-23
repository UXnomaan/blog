---
template: BlogPost
path: /automated-resume
date: 2022-01-21T03:02:47.457Z
title: "Autopilot for your resume"
summary: Say goodbye to Resume_final.docx, say hello to version controlled, auto deployed and beautiful resumes!

thumbnail: ./static/img/Group 1.png
tags:
  - automation
  - resume
---

Keeping a resume up-to-date is a task that we usually don't pay attention to until it's time to look for a new job. I have gone through different iterations from using word documents to using Apple Page to create a resume I like. You have probably spent of hours on making sure all the dates line up and everything fits into a page so did I.

In order to remove all the overhead related to keeping an updated resume I decided to look into <https://jsonresume.org/>, a JSON schema for your resume. There are pre-made [themes](https://www.npmjs.com/search?ranking=maintenance&q=jsonresume-theme) that you can use as well so all you need to do is create a JSON file with your resume information.

JSON resume project has a CLI that lets you generate PDF and HTML version of your resume. Hmmm, this means I can put it up online as well. This is why I ended up creating a [GitHub Action](https://github.com/UXnomaan/resume/blob/main/.github/workflows/build.yml) to deploy to a domain I own on each merge to master. You might ask now I have to deal with hosting it. Netlify can take care of that for you, there is a [GitHub Action](https://github.com/nwtgck/actions-netlify) for that.

This approach makes it extremely easy to keep an updated resume, try different themes and spend 0 minutes aligning!

Feel free to fork this repo and add your information: <https://github.com/UXnomaan/resume>

You can see my resume at: <https://resume.nomaan.tech/> and the PDF version at: <https://resume.nomaan.tech/ahgharian-nomaan-resume.pdf>

<center>
<object data="https://resume.nomaan.tech/ahgharian-nomaan-resume.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="https://resume.nomaan.tech/ahgharian-nomaan-resume.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="https://resume.nomaan.tech/ahgharian-nomaan-resume.pdf">Download PDF</a>.</p>
    </embed>
</object>
</center>
