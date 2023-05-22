can you please evaluate the the following and provide scripts / snippets to learn the material? 


- So, in the last video, we saw how we could create
0:06
a constructor function, use the new keyword
0:09
to generate new objects that conform
0:11
to some sort of specification or pattern.
0:14
In this case, a triangle object.
0:15
But there is one thing I haven't shown you,
0:18
one possible negative with this approach.
0:21
It has to do with the way we're adding methods
0:23
and to understand what the issue is.
0:26
We need to discuss prototypes in JavaScript.
0:28
Now this is a bigger topic we will revisit later on.
0:32
So, I'm just gonna kind of skim over it.
0:34
Give you the basics here.
0:35
It's kind of could be fun we'll see, okay.
0:38
So, when we make a triangle in our case,
0:41
take a look at try one for example,
0:44
a variable I already instantiated over here.
0:47
It has A and B as properties on this object
0:51
and it has getArea and getHypotenuse
0:54
as properties on this object.
0:56
When I make something like a set new set
0:59
I'll call this myset const,
1:01
myset equals a new set same syntax, new,
1:05
and then a constructor function
1:07
this time it's just a built-in set.
1:09
Let's look at myset.
1:12
It doesn't appear to have any methods.
1:15
It has a size property, myset.size is zero
1:19
but how am I able to add something to the set like 45?
1:23
Where is that add method?
1:25
It's not in here like it was for our triangle.
1:29
Well, it is on the prototype the set prototype.
1:34
Here are all of these methods that we have on every set
1:37
add, clear, delete, for each, has, keys and so on.
1:42
This is a really important distinction.
1:44
You've probably noticed when you're looking at the docs
1:46
let's say at something like an array,
1:48
the array docs on MDN to look at all the methods
1:51
on the left-hand side,
1:53
we can see that almost all of them start
1:55
with array.prototype, array.prototype.every,
2:00
.find, .includes all of these methods
2:03
are on this array.prototype.
2:06
So, what is it?
2:07
Well, without going into too much detail here,
2:10
a prototype is just an object and usually contains a bunch
2:13
of methods, sometimes different properties as well
2:16
or different non-method properties.
2:18
And it contains the functionality,
2:20
the methods that let's say every set would use.
2:23
And we can actually see the prototype
2:25
on its own by calling set.prototype.
2:28
This gives us an object.
2:30
This is the object that defines add and clear and delete
2:34
and for each.
2:35
We could look at array.prototype.
2:38
This is another object.
2:40
It's a special object.
2:41
It has a special place in the world of JavaScript.
2:44
It's predefined for us.
2:45
A radar prototype, this is an object that contains all
2:49
of the standard array methods.
2:51
And every array we create has access to these methods.
2:55
Just like every set that we make
2:57
has access to these methods.
3:00
Even though the methods don't exist,
3:01
on the individual object that we created the set.
3:05
Like we can see here, if I close that down,
3:07
those methods aren't here.
3:09
They're located on the prototype.
3:12
Now this is kinda confusing.
3:13
You probably have to notice
3:14
this double underscore proto double underscore.
3:17
That is a property name that references
3:20
the prototype of this object.
3:23
And if we look at an array,
3:25
like just a empty array and take a look,
3:27
it has a double underscore proto property
3:30
and it references the array prototype.
3:33
And we could double check that by doing this right here.
3:38
If we access that prototype triple equals array.prototype
3:44
they are referencing the exact same object.
3:47
So, this is the actual prototype object.
3:49
This is just a property on an array
3:52
that references the prototype object.
3:55
So, that's all we're gonna say about it for now.
3:57
These prototypes are objects that store functionality
4:00
that can be used across any instance.
4:03
What I'm doing with my triangle right now,
4:05
is adding a getArea and a getHypotenuse
4:08
to every single triangle.
4:10
But we could instead put them on the prototype
4:13
and it would work just the same.
4:15
As far as how it works or why it works,
4:17
that is something we'll get into another time later on.
4:20
So, first I'll show you that we can do things
4:22
like this right here.
4:24
Array.prototype.
4:25
how about we change push,
4:29
let's change push
4:31
and give it a new function.
4:34
And this function let's say it accepts an argument.
4:38
We'll call it val.
4:40
We will come to that log.
4:43
So, you want to add, let's do a template string template.
4:48
Literal you want to add val and then cancel .log
4:54
Sorry, don't feel like it.
4:58
Okay.
4:59
What I'm doing here is accessing the array prototype object.
5:03
The one special object that contains all
5:06
of these array methods and I'm overwriting the push method.
5:10
Which is not really a good idea ever
5:12
but I'm doing it to illustrate how this works.
5:15
Anytime I make a new array, I just refresh my page.
5:18
The code ran, I'll make a new array.
5:20
Let's call it nums equals one, two, three.
5:23
I call nums.push and I try and push nine
5:28
so, you want to add nine?
5:29
Sorry don't feel like it.
5:31
I look at nums that value is not pushed on.
5:34
I just changed the push method for every single array.
5:39
Not a good idea, but it illustrates how this works.
5:42
We're able to change this one prototype this object,
5:46
one method on it called push.
5:47
And now every array I make, I can make an empty one
5:50
and try and push five onto it or four.
5:53
I get the same thing.
5:55
So, we could attempt the same with our triangle.
5:58
Right now, that's not what's happening.
6:00
Every triangle instance has its own getArea
6:03
and its own getHypotenus.
6:05
The last thing I'll say
6:06
about this as far as changing built-in prototypes
6:09
it's not something you wanna do
6:11
there is one situation where it's acceptable
6:15
which has to do with polyfills.
6:17
So, anytime there's a newer method in JavaScript
6:21
that is not implemented across all the browsers,
6:24
like this string includes method
6:26
which is a newer method does not have IE support.
6:30
If you actually look at the docs,
6:31
there's a polyfill section here.
6:34
And this includes some code that you can add
6:36
to your your files, your scripts, that checks
6:39
if there's an includes method on string.prototype,
6:42
then don't do any of this.
6:44
But if there is not, it defines stringed.prototype.includes.
6:48
So, includes is a newer method.
6:50
It's not fully supported in every browser.
6:53
This is a way of checking if something is included already
6:56
it shouldn't use the word includes.
6:58
If something exists in this environment,
7:00
whichever browser the code runs in
7:02
and if it's not there, it's defined.
7:04
That's really the only situation where you should do that.
7:07
Okay.
7:08
So, now back to our triangles, how do we fix this
7:12
so that we can add these methods to the triangle prototype
7:16
rather than to every individual triangle we make,
7:19
we don't need a separate copy,
7:22
when I say separate copy I mean,
7:23
every time we make a new triangle with this syntax
7:26
we're making a brand new function, a brand new function
7:30
and they are unique separate functions
7:31
even though they do the exact same thing,
7:34
just like with arrays there's only one array push
7:37
we're accessing array push
7:39
from the prototype where it's defined.
7:41
Let's do that here.
7:43
So, it looks like this,
7:45
we have to do it on a separate line, triangle.prototype.
7:49
And if I look at that right now in my code
7:52
I just type a triangle.prototype, it does exist.
7:57
There's just not much to see, but it is a thing.
8:00
So, let's try it.
8:01
Triangle.prototype.getArea equals
8:07
and then I can just copy this exact function over
8:11
like that and then get rid of that there.
8:15
And I'll do the same thing for our getHypotenuse.
8:20
Triangle.getHypotenuse equals this function
8:25
triangle.prototype.
8:27
There we go.
8:29
So, now we are defining this on a single special object
8:32
called triangle.prototype.
8:34
And every time we make a new triangle,
8:37
that object not only will have A and B set up,
8:40
but it will also know that it's prototype is triangle
8:45
That's part of the magic of this new keyword.
8:48
So, let's try it.
8:49
Let's take a look at triangle one.
8:52
All that we see is A and B,
8:54
but if we try triangleone.getArea,
9:00
we get six.
9:02
If we do getHypotenuse,
9:05
we get five.
9:06
If we do triangletwo.getArea,
9:09
we get 54.
9:10
If we do triangletwo.getHypotenuse, we get 15.
9:15
But again, we look at triangle one and triangle two.
9:18
They do not have their own copy
9:20
of getHypotenuse and getArea
9:23
instead, you would have to open
9:24
this up in order to see where they're defined
9:27
on the triangle prototype
9:28
which we can take a look at one more time triangle.prototype
9:32
There it is getArea, getHypotenuse.
9:36
So, why am I bringing this up?
9:38
I am of the opinion that this makes it easier to understand
9:42
why you would use a class.
9:44
Classes allow us to get this same functionality
9:47
without having to define something
9:50
like we have here, a function
9:51
and then separately adding methods to the prototype.
9:55
This is kind of annoying to have
9:57
our data separate from our functionality.
10:00
Using a class, which we'll see in the very next video.
10:03
We can group our methods together with our values
10:06
in one class, we don't have to talk about the prototype.
10:09
We don't have to reference it at all.
10:11
And we get the same outcome.
10:13
It's a nice, easy way of getting this outcome
10:17
without having to write this code separately.
10:19
So, that's pretty much the only reason
10:21
I'm showing it to you right now.
10:22
I think it helps you understand
10:24
or hopefully it will help you understand
10:25
the benefit of classes.
10:27
So, I'll stop here.
10:28
That was a lot.
10:30
If you're struggling with it,
10:31
I wouldn't bang your head against anything.
10:34
Not your desk, not the wall, nothing really.
10:37
I wouldn't bang your head because it's not a big deal.
10:40
This is something we'll come back to,
10:42
nothing to stress over.
10:44
It is kind of fun to do things
10:45
like this I don't recommend you actually do it
10:48
unless you're working with a polyfill once again.
10:51
But otherwise, all you need to remember
10:53
for now is that triangle.prototype,
10:56
a radar prototype, set up prototype
10:58
they are special objects where we commonly define methods
11:01
or methods are defined for us like in the case
11:04
of arrays and sets, we're not defining those methods.
11:07
They're defined on this special object, the prototype object
11:10
that the individual instances, the individual arrays
11:13
or sets or triangles in our case have access to,
11:17
even though they don't have their own copy
11:19
of these methods anymore they can still access getArea
11:21
and getHypotenuse news as we saw.
11:24
So, it's one centralized place
11:26
one object to define those methods.
11:28
And it's the same method
11:30
which I guess I should show that here
11:34
triangleone.getArea
11:35
we'll just pick one equals triangletwo.getArea.
11:39
Now I'm not executing the functions.
11:41
I'm referencing them.
11:44
And those references are the same.
11:46
If we had run this before
11:48
when we had the methods added in here
11:50
this .getArea, every triangle would have its own copy.
11:54
Okay.
11:55
Let's move on to classes.
11:56
(digital music)