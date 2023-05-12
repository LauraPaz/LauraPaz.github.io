---
layout: page
title: About
permalink: /ab/
---


# Alfredo's Pizza Café, or Pizza by Alfredo?
### A small guide to restaurant inspections in NY

You've heard it! New York, the city that never sleeps, the big apple and a thousand other names for the most famous city in the world. Even if you've never been there, you know all about it: Streets, buildings, statues, taxis, people, all of it is in movies, series, photos and all kinds of media we see and hear every day. But apart from friends, heroes, detectives and criminals, there is always another protagonist that we know all about:

<p align="center">
  <img src="../static/ab/extra/joey_food.gif"/>
</p>


Relax, **it's food**.

In the city that attracts people from every corner of the world, you can find any cuisine you can imagine and more: From Italian to Mexican and from Greek to Colombian, everything is possible. But with everything at your feet (or at your fingertips, considering that today you can order almost anything to be delivered), the question begs to be asked.  It's the most simple and difficult question to answer, whether it's coming from a lifelong New Yorker or a first-time visitor: "Where should I eat in New York City?" Your casual magazine "article" will tell you everything about this week's hyped restaurants and how "fresh" the menu is, according to the relevant blog authority. But today, we are taking it one step further: We ‘re going to tell you how clean (or not!) it is and how you can find out yourself. And in order to achieve that, we turned to the professionals.

The Department of Health and Mental Hygiene (DOHMH) of New York maintains and daily updates a dataset with the results of every restaurant inspection it performs in the city of NY. Tens of thousands of entries, contain all there is to know about how clean and safe restaurants are and how much effort they put in taking care of their customers. With the proper analytic approach, this dataset was transformed into a complete overview of the situation of the restaurant scene of the city to help you navigate through it and avoid traps that will make you throw that disgusting piece of pizza in the trash, or even worse, take you to the emergency room!

<p align="center"><iframe src="../static/ab/extra/kevin.gif" height=250 style="border:none;"></iframe><iframe src="../static/ab/extra/michael.gif" height=250 style="border:none;"></iframe></p>

The first thing you need to know is how the DOHMH grades restaurants after each inspection. This table will give an idea:

![Grading guide](../static/ab/extra/grading.jpg)

Now let's get into specifics. The first thing we looked for is the distribution of inspections among districts. New York is divided in boroughs, so we counted the number of inspections, types and rates of violations and closures in each borough. The results of this analysis indicate that the absolute number of inspections and violations vary greatly between boroughs, with more than ten times more inspections taking place in Manhattan compared to Staten Island. Let's take a look in the following bar plot:

<p align="center">
  <img src="../static/ab/plots/occurrences_per_borough.png" height=250/>
</p>

But the number of inspections only tells which place has the most restaurants, and we are not surprised it's Manhattan. How about looking into how many of these end up in a bad grade? This map below illustrates the differences:

<iframe src="../static/ab/plots/negative_outcome_boro_rate.html" width="100%" height="420" style="border:none;"></iframe>

What comes as a surprise is the rate at which these inspections end up in a negative outcome. In general, more than 98% of the total inspections end up finding at least one violation! Terrifying right? Well, in all fairness, a lot of these cases involve minor, and even trivial violations, like "Absence of a "Wash Your Hands" sign in the restroom" or similar. A clearer picture of where the serious violations happen, might come from the rate of inspections that end up in a restaurants closure. The following map gives us this information and even divides the city into neighborhoods:

<iframe src="../static/ab/plots/closures_neighborhood_rate.html" width="100%" height="420" style="border:none;"></iframe>

And, as far as grades go, here is the distributions of grades received by restaurants in each borough:

<p align="center">
  <img src="../static/ab/plots/horizontal_grades_per_borough.png" height=400/>
</p>

After investigating the spatial distribution of inspections it's time to focus on how inspections progress through time. Here the most important, and admittedly expected, thing, is the total absence of inspections during the peak of the corona-virus pandemic. It is a fact that New York was hit very hard by COVID-19, being the city facing the most difficulties in the USA. Between the middle of March 2020 and July 2021, for the greatest part of which time restaurants were closed, almost no inspections took place, leaving a huge gap in the calendar analysis. This is clearly illustrated in this bar plot:

![Occurrences per month](../static/ab/plots/occurrences_per_month.png)

In what looks like an attempt to compensate for the lost time, inspections skyrocketed the following year, with more than three-times more inspections taking place in 2022 than 2019! This is again easy to see in this calendar plot where you can even see the differences between days of the week (apparently, no inspections happen during the weekend!). 

![Calplot](../static/ab/plots/calplot.png)

But does this trend through time hold true for all boroughs? And are inspections equally strict in every place? Did the inspectors return in a bad mood, having to go back to work after months of chilling at home? This interactive bar plot has all the answers:

<iframe src="../static/ab/plots/closure_rate_bokeh.html" width="100%" height="420" style="border:none;"></iframe>

Now, if you are like us, you are wondering how each type of cuisine performs compared to others. Is it more common for one type of restaurant to be generally "dingy", while others are more commonly "top notch"? We used the data to compare the performance of each type of cuisine and reached to some very interesting conclusions. The bar plot below gives the answer in a single glance, illustrating the rate at which each cuisine type receives each grade:

<iframe src="../static/ab/plots/grade_distribution_by_cuisine.html" width="100%" height="600" style="border:none;"></iframe>

That doesn't mean that you should fight your craving for butter-chicken and go for a doughnut instead! The distribution of the score for each type of restaurant can vary greatly, and a really bad place can ruin the reputation of a whole cuisine. In the following boxplot, we see how spread out the distribution of the scores of each cuisine can be:

![Boxplots](../static/ab/plots/boxplots.png)

In the end, the purpose of this analysis is to give you the necessary insight to navigate through the city and find a place you can confidently dine in!  Let's say you are in New York, and you don't have unlimited time or money. You are hungry and you want to eat in a place that you can trust to be professional with its quality. We have the right tool for the job! Through the magic of data analysis, we have put together an interactive scattermap where you can look for those restaurants that received each type of grade, all over the city. This way you know which places to choose and which to avoid!

<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {font-family: Arial;}

/* Style the tab */
.tab {
  overflow: hidden;
  border: 1px solid #ccc;
  background-color: #f1f1f1;
}

/* Style the buttons inside the tab */
.tab button {
  background-color: inherit;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 14px 16px;
  transition: 0.3s;
  font-size: 17px;
}

/* Change background color of buttons on hover */
.tab button:hover {
  background-color: #ddd;
}

/* Create an active/current tablink class */
.tab button.active {
  background-color: #ccc;
}

/* Style the tab content */
.tabcontent {
  padding: 6px 12px;
  border: 1px solid #ccc;
  border-top: none;
}

</style>
</head>
<body>

<div class="tab">
  <button class="tablinks" onclick="openCity(event, 'American')">American</button>
  <button class="tablinks" onclick="openCity(event, 'Chinese')">Chinese</button>
  <button class="tablinks" onclick="openCity(event, 'Pizza')">Pizza</button>
  <button class="tablinks" onclick="openCity(event, 'Coffee')">Coffee/Tea</button>
  <button class="tablinks" onclick="openCity(event, 'Latin')">Latin American</button>
  <button class="tablinks" onclick="openCity(event, 'Mexican')">Mexican</button>
  <button class="tablinks" onclick="openCity(event, 'Japanese')">Japanese</button>
  <button class="tablinks" onclick="openCity(event, 'Bakery')">Bakery</button>
</div>

<div id="American" class="tabcontent">
  <iframe src="../static/ab/grademaps/american.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Chinese" class="tabcontent">
  <iframe src="../static/ab/grademaps/chinese.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Pizza" class="tabcontent">
  <iframe src="../static/ab/grademaps/pizza.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Coffee" class="tabcontent">
  <iframe src="../static/ab/grademaps/coffee_tea.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Latin" class="tabcontent">
  <iframe src="../static/ab/grademaps/latin american.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Mexican" class="tabcontent">
  <iframe src="../static/ab/grademaps/mexican.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Japanese" class="tabcontent">
  <iframe src="../static/ab/grademaps/japanese.html" width="100%" height="420" style="border:none;"></iframe>
</div>

<div id="Bakery" class="tabcontent">
  <iframe src="../static/ab/grademaps/bakery products_desserts.html" width="100%" height="420" style="border:none;"></iframe>
</div>


<script>
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("tabcontent");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].style.position = 'absolute';
    tabcontent[i].style.left = '-9999px';
  }
</script>

<script>
function openCity(evt, cityName) {
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("tabcontent");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].style.position = 'absolute';
    tabcontent[i].style.left = '-9999px';
  }
  tablinks = document.getElementsByClassName("tablinks");
  for (i = 0; i < tablinks.length; i++) {
    tablinks[i].className = tablinks[i].className.replace(" active", "");
  }
  document.getElementById(cityName).style.position = 'static';
  document.getElementById(cityName).style.left = 'auto';
  document.getElementById(cityName).getElementsByTagName("iframe")[0].style.position = 'static';
  document.getElementById(cityName).getElementsByTagName("iframe")[0].style.left = 'auto';
  document.getElementById(cityName).getElementsByTagName("iframe")[0].style.top = 'auto';
  evt.currentTarget.className += " active";
}
</script>

   
</body>
</html> 

