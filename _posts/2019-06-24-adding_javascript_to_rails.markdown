---
layout: post
title:      "Adding Javascript to Rails"
date:       2019-06-24 18:58:07 +0000
permalink:  adding_javascript_to_rails
---


Since starting this journey we have been tasked with understanding core aspects of modern web development.  None have been more difficult than working with Javascript and gaining an appreciation for everyone using it in their daily lives.  How can something which on the surface when read appear so simple and elegant but when to using it myself, I feel a frustration that I haven't experienced in the 5 months I have been a member of this program.  But here is the kicker, I thoroughly enjoy it!   This is exactly what I needed to reenforce my commitment to completing this bootcamp.  Not only was this difficult but dare I say it made me question everything I have been doing so far.  Maybe I am being too hard on myself, afterall I did say I enjoyed every head shaking moment.  All I want to do now is write in Javascript!  Let's get into how this project was applied to my Rails project and why it makes such a huge difference.

When you go to any website, or almost any website you begin to recognize that the app does two things, 

1. The website tends to load information before you need it
2. The website displays information without reloading the page
3. The website also renders user input values without reloading the page

For a clearer picture at how this works you dont have to look any further than one of the worlds most heavily trafficed sites such as Facebook, IMDB, and Amazon.  My application relies on rendering user input values in an asynchronous manner.  So the user can fill out a quick form and render that form and append it to a table body.  This without a shadow of a doubt has been the most difficult task yet.  I have become too accustomed to Ruby methods and it took a bit longer than expected to get the hang of it.  In order to get the page to function as expected I needed to make two things

1. A Javascript file to construct the data and fetch the information
2. a jQuery script to use the Javascript file and prevent default actions that occur on user submit. 

The Javascript file needs a constructor to manage the information being passed in.  Very similar to a Ruby class and instances.  
```
class Objective {
    constructor(id, name, description, user_id, due_date, group_id, completed){
    this.id = id
    this.name = name
    this.description = description
    this.user_id = user_id
    this.due_date = due_date
    this.group_id = group_id
    this.completed = completed
    this.render()
    }
```

and a render function

```
render() {
        $('table').find('tbody').append(`
        <tr>
                      <td id="postUser">${this.user_id}</td>
                      <td id="postName">${this.name}</td>
                      <td id="postDescription">${this.description}</td>
                      <td id="postDate">${this.due_date}</td>
                      <td id="postComplete">${this.completed}</td>
                      <td><button>show</button></td>
                      <td><button>edit</button></td>
                      <td><button>delete</button>
                      </td>
                    </tr>`)
        
        }
```

The first line of the render() function is

```
 $('table').find('tbody').append(
```

This finds the table body and appends the data following it to the body of the html tag.  

The index.js file contains a jQuesry script to allowing everything to come together and reset the form allowing the user to quickly render a new Objective

```
  <script type="text/javascript" charset="utf-8">
    $(function () {
      $('form').submit(function (event) {
        event.preventDefault();
        const checked = this.completed == true ? 'completed' : ''
        let values = $(this).serialize();
        let posting = $.post('/objectives.json', values);
        posting.done(function (data) {
          const newObj = new Objective(data.id, data.name, data.description, data.user.name, data.due_date, data.group_id, data.completed) 
          
          $("form")[0].reset()
        });
      });
    });
  </script>
```

Thats it!  Looks incredibly simple but looks can be decieving.  I want to finish this by thanking my instructor for his patience and willingness to assist in helping me understand where I was going wrong, and bringing me to solutions that I may have not had without his help.  Flatiron School choose their instructors well and I continue to recommend this school to anyone that wishes to learn how to code.  

Next is our Final Project and I can't wait to show everyone how well this school has done in educating me.  To think we started off with the most simplest terms like boolean, hashes, and the ever dreaded Regex to building webpages using javascript and now React and Redux.  The journey is almost over, I'll see you all at the finish line!

