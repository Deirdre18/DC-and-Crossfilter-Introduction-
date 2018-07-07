## This are DC.js and Crossfilter.js lessons (from Code Institute Full-Stack Diploma course). Transcription from lessons, included in comments sections in the code. 

# DC.js and Crossfilter.js

1. What is it?

DC.js and Crossfilter.js

(DC LINKS)
http://dc-js.github.io/dc.js/
https://cdnjs.com/libraries/dc

(CROSS FILTER LINKS)
https://cdnjs.com/libraries/crossfilter

2. What does it do?

The DC.js library provides prebuilt charts types for D3. Crossfilter.js enables the charts to be interactive and interdependent on the same dataset.

3. How do you use it?

Provide Crossfilter with a dataset that is charted with dc.js

LESSON:

Now Crossfilter allows you to work with data to make the charts rendered by DC to make them interactive so if you click on a
particular chart on a dashboard another related chart that is a chart that's
bound to the same data set can react to that click and maybe represent a subset
of the data that was represented in another chart so it's a way of
interacting visually interacting with with your data without having to use
traditional drop-down widgets are free text fields where you're typing in
search strings when you want to filter the data in some way to use these three
libraries you import them in a particular order so you your first
script is d3 your second script should be cross filter and your third should be
DC because dimensional charting depends on cross filter and they both depend on
d3 so the order is important if you if you change the order you might get
unexpected results now the data we're using here is something that you might
typically see on an Excel spreadsheet it's slightly different in data we were
playing with earlier on which was just integer based so this is a mixture of
strings and numerical values so what we want to do is to bind our data to a
cross filter object you know I mentioned that cross filter allows you to work
with data and engage in what's called two-way binding between charts so don't
worry too much about the syntax here in this unit we'll be going through this
again and again it's just to get a sense the shape of the of the syntax and the
objects and functions at play here so once we use filter we create a variable
called n DX it's just a it's a convention just like the diene in d3 and
then we try to get a dimension and a dimension is a particular column of data
that you want to use and to get its values in our case we want to use the
name dimension and then we want to group they the names together in order to get
some values from them now cross filters done its job up to a point here then we
use DC which is dimensional charting to create a bar chart because as I
mentioned DC has built-in charting for us that's built upon d3
let's have a look at that you can see here we have easily created charts we
don't have to go to the trouble of manually creating them to the extent
that we did earlier in the d3 so this is just a brief introduction to DC and
cross filter we will explore these a lot more in the coming units.


# Multiple Charts with DC.js and Crossfilter.js

1. What is it?

DC.js and Crossfilter.js

(DC LINKS) - Links from lesson:
http://dc-js.github.io/dc.js/
https://cdnjs.com/libraries/dc

(CROSS FILTER LINKS) - Link from lesson:
https://cdnjs.com/libraries/crossfilter

2. What does it do?

The DC.js library provides prebuilt charts types for D3. Crossfilter.js enables the charts to be interactive and interdependent on the same dataset.

3. How do you use it?

Bind your dataset to an instance of Crossfilter. Then create one or more charts using DC. DC uses Crossfilter for its data source. Interacting with a chart by clicking, hovering or dragging on the rendered data automatically updates other charts that are also bound within.

LESSON:

In our dataset we have three customers Tom, Bob and Alice who shop in two
stores - either Acme or the Big Co. across two states - New York and Florida
So let's create a dashboard that reflects those spend trends and the
location trends in the shop trends for example are the store trends that they
buy their products in so in order to do that we are going to create three
different charts one for the store one for the state and one for the person and
to do that we need to create a div to target our charts for each dimension of
data so remember that we're going to work with three dimensions of data one
will be the name dimension the second will be the store dimension and the
third one would be a state dimension and all of that will be based around the
dimension of spend okay so we're creating three divs give each one a
unique ID and we will create a bar chart for each div
so we just can rename our parts of our code from the last example and mainly
it's a case of copy and paste with some minor changes so here we're creating our
store dimension I'm going to pluck we're using DC to pluck all store elements
from our data set and we're going to group and reduce some so we're going to
group all and all the stores and reduce some then what it does is it sums up the
amount for each store they spend at each store and magically maps that and binds
that to to our chart a lot of this will seem a bit like magic in the beginning
as you get used to these because so much effort and heavy lifting is taken care
of underneath the hood via cross filter and DC for us but it's very it's hugely
powerful and you can get up to speed creating rich interactive dashboards
quite quickly which is what we're going to do now so let's change the X access
label for each luckily we have two of our three charts in place we'll get the
third one a place now and then once we have that done we will clean up the
alignment of the the chart elements
so now we're going to create a state dimension which will represent products
purchased by state and they'll be two bars and it will be New York and Florida
will be the spend in Florida and the spend in in New York we changed the
dimension on line 84 we change the dimension for each of these bar charts
and we have the makings of a dashboard an interactive dashboard but they the
layout isn't isn't it layout could be a lot better so let's clean that up
so to do that we're going to add a style so let's put a style Block in the head
of our HTML file and we target all the div's so what we want to do is we want to
they we want the charts to display in a vertical order down the page so to do
that the easiest way to do that is to clear left apply the clear left styler
and we have our three charts now remember each chart is bound
to the same data set and DC makes our d3 graphics it makes them interactive event
driven so if you click on these the data changes so I if I click on Alice I can
find out what Alice purchased in Acme versus the company and Florida versus
New York same as Bob and same as Tom
it's very powerful so I don't have to filter and using drop-down lists or
entering in the person's name just clicking on they the the chart itself
results in events being triggered and filtering takes place automatically for
us very very powerful

