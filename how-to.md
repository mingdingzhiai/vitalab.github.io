---
layout: page
title: How-to
permalink: /howto/
---



## How to add a review

The process for adding reviews is _git-centric_. Basically, **you just need to add a file to the repo and make a pull request**. Let's go into the details :

0.  Send an e-mail to Pierre-Marc Jodoin asking him to include you as a member of the [github.com/vitalab](https://github.com/vitalab) organization.
1.  Clone the [`vitalab.github.io`](https://github.com/vitalab/vitalab.github.io) repo on your computer.
2.  Determine the category in which you will add your post. Categories are managed using folders :  
    
    ~~~
    _posts/           # A post added here will have no category
    course/
        _posts/       # A post added here will be in the "course" category
    machine-learning/
        _posts/       # Same thing for the "machine-learning" category
    ...               # There are other categories, you can add one too.
    ~~~
3.  Create a file `YYYY-MM-DD-title-of-your-review.markdown` and put it in right folder (see above).  
It is **important that you respect this format : date at the beginning and no spaces.** Else the page won't build properly. Here is an example of a valid name : `2017-01-31-going-deeper-with-convolutions.markdown`.
4.  Copy this template in your new file :  
    
    ``` markdown
    ---
    layout: review
    title:  Title of your Review
    author: Your name
    link:   http://link.to.the.paper.com
    tags:   convolutional-networks deep-learning  # put relevant tags here
    ---
    
    Content of your review.
    ```
    You can [preview your post while you write it](#previewing-your-post-locally) ; see the next section about this.
5.  **Make a new branch**, commit your file and push your branch.
6.  [**Create a pull request**](https://github.com/vitalab/vitalab.github.io/compare) on the repo's github page.
7.  **Add reviewers**: everyone that you think are knowledgeable about the subject or simply would be interested in your review.
8.  When every reviewer approved your branch, **merge your branch and delete it**.

## How to preview your post locally

This site is built around [**Jekyll**](https://jekyllrb.com/). Jekyll takes all the markdown files and generates a static html website.

1.  [Install Ruby using rbenv](/how-to-install-ruby). Don't use `apt-get` since its version of Ruby is too old.
2.  Install Jekyll by running : `gem install bundler jekyll`.
3.  Go where you cloned the repo and run : `bundle install`. This will install the dependencies for our Jekyll site.
4.  Run a local webserver using : `bundle exec jekyll serve`.
5.  Access the site locally at : <http://127.0.0.1:4000/>

Note that the site is automatically rebuilt when change a file.