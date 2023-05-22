can you please evaluate the the following and provide scripts / snippets to learn the material? 

So classes are a new short syntax to create patterns
0:10
for objects or blueprints for functionality.
0:14
We define a class which will act as a pattern or a template
0:17
for a particular type of object we want to create.
0:21
So let me show you a simple example.
0:23
The first thing you need to know is the class keyword,
0:26
class, and then some name of our class,
0:28
if we go with our triangle example,
0:31
that makes us a triangle class.
0:34
In this class we'll define a pattern for our triangles,
0:37
that this thing itself here,
0:39
will not be a triangle object,
0:41
this is the template.
0:43
Then we need to instantiate new triangles
0:45
with this new triangle, with parentheses.
0:49
So no parentheses here sometimes to see students do that,
0:53
you're not defining a function.
0:55
At least you're not using function Syntax,
0:57
instead it's just class,
0:58
and then some identifier for the class.
1:01
And typically you should use a capital letter.
1:04
You should always use a capital letter.
1:06
It just so people know this is a class,
1:08
this is not a function named triangle,
1:11
this is not a particular instance of triangle,
1:13
because we could make a particular triangle like this,
1:17
const triangle equals a new triangle object
1:22
or a new triangle instance.
1:23
That capital letter makes it clear,
1:25
this is the class we're trying to create an object from.
1:30
And then to add methods to our class,
1:33
we just define a method in here.
1:34
Let's go with a really simple one, greet.
1:37
I don't know why a triangle would greet,
1:39
but we'll start with that,
1:40
console dot log.
1:42
Hello from triangle.
1:46
All right.
1:47
So let's Tri making a couple of new triangles.
1:49
Let's go with const firstTri,
1:53
equals new triangle.
1:58
This triangle has no properties,
1:59
or it has no data that we're storing on it.
2:02
It does one thing and one thing only,
2:04
it has a method called greet every time I make a triangle.
2:07
Let's do secondTri.
2:10
We'll get a different object that has a greet method.
2:15
Let's take a look first at firstTri.
2:19
Okay.
2:19
So if we open it up,
2:21
it looks like it's a completely empty object,
2:23
but if we open up this proto thing,
2:26
you'll see there is a greet function or a method,
2:29
technically it's called greet.
2:31
We did not have to add it to first triangle
2:34
or firstTri manually,
2:36
it was defined in this pattern, the class,
2:39
and I could execute it.
2:40
FirstTri dot greet.
2:45
Okay, hello from triangle.
2:46
Not very exciting, but it does work.
2:48
If we did secondTri dot greet,
2:53
same thing.
2:54
Hello from triangle.
2:56
So at this point,
2:57
this triangle class seems like very unnecessary.
3:00
We could just have a greet function on its own
3:02
without any classes, without any objects,
3:05
we would just call greet.
3:06
Next let's change that a little bit.
3:08
Let's add a new method here called display.
3:12
And display is going to reference this dot a or this stop b,
3:17
the different sides of the triangle,
3:19
which are triangles at the moment do not have,
3:21
there are no sides on these triangles,
3:23
we're not adding any data, but we'll get there.
3:26
Let's just console dot log,
3:28
a simple string template literal,
3:30
and say, Hmm, triangle with the sides of,
3:36
and then we'll add in a or this dot a,
3:42
and then after that,
3:44
we'll do and this dot b.
3:48
So what do you expect to happen when I run my code again,
3:51
and we look at firstTri or secondTri,
3:54
and then I execute display?
3:57
First if we look at firstTri,
4:00
it does have a display method now.
4:02
And if we execute that firstTri dots display,
4:09
triangles with sides of undefined and undefined.
4:13
Okay, so let's fix that.
4:14
Let's add in firstTri dot a equals three,
4:19
firstTri dot B equals four,
4:23
and then secondTri dot a equals nine,
4:28
and secondTri dot b equals 12.
4:32
We're manually adding in those properties
4:35
to our triangle objects,
4:37
so they're not added to the class,
4:39
we're adding them to the instance,
4:41
when we call new triangle with parenthesis
4:43
and the new keyword,
4:45
we're creating a new object based off of this template.
4:48
And right now, this template, our class,
4:50
all that it specifies is that each triangle object
4:53
has two methods.
4:54
So I'm gonna run my code again.
4:56
Now, if we look at first triangle,
4:58
we do have a and b,
5:00
these instances that we get back from calling new triangle
5:03
are just regular JavaScript objects
5:05
we can add and update properties at will
5:08
using the dots syntax or the square bracket syntax,
5:10
if we prefer that for some reason, totally fine.
5:15
Now, if we run firstTri dot display,
5:23
take a look,
5:24
triangle with sides of three and four.
5:27
So inside of these methods, if we reference this,
5:30
it refers to the particular instance of this triangle class,
5:34
not the class itself,
5:36
but the instance this triangle or this triangle.
5:40
So if we try secondTri dot display,
5:43
triangle with sides of nine and twelve
5:46
Okay.
5:47
So now we've defined a pattern for triangle.
5:49
It has methods.
5:51
One method is stupid, it does the same thing every time,
5:53
it console dot logs, hello from triangle.
5:56
The second method is equally stupid in that it's useless,
6:00
but it is referencing this dot a and this dot b,
6:04
which are properties that this method assumes
6:06
exist on the individual instances.
6:09
So the class is up here,
6:12
it's a pattern.
6:13
These are instances of triangle,
6:16
and then we're manually adding in a and b each time.
6:21
And if you're thinking there must be a better way.
6:23
Why do we have to do this like right here,
6:25
one line to set a and then b another line for a and b,
6:29
there is a better way.
6:30
We're about to see it in the next video.
6:32
We can pass values in when we instantiate a new triangle,
6:36
rather than doing it this way.
6:38
So that's what we'll see next.
6:39
What we've seen so far is that when we define a class,
6:42
first of all the identifier that you use,
6:45
should start with a capital letter to make it clear,
6:46
this is a class.
6:48
We don't have parentheses here,
6:50
we have our curly braces,
6:51
and then inside we can define methods.
6:54
And these methods are not actually added
6:56
to the individual instance,
6:58
like first triangle or second triangle.
7:00
They are added to the triangle dot prototype.
7:04
As we saw in the last video,
7:06
prototypes are a place or an object,
7:08
in this case the triangle prototype
7:10
is an object that will contain shared methods.
7:13
There's no reason that every single triangle
7:15
has to have its own unique greet or display.
7:19
These methods still have access to this dot a and this dot b
7:22
which are defined on the instances,
7:25
but they don't have to be redefined.
7:27
We don't have to have one version of display
7:29
for this triangle and then a completely new function
7:32
for this triangle.
7:33
They can run the same function and get a different outcome
7:36
or different output, depending on a and b,
7:38
which exists on the actual objects.
7:42
So we can define these methods in a class,
7:44
then we instantiate new instances, a new object,
7:48
based off of that pattern,
7:49
and that's pretty much it.
7:50
That's what we've seen.
7:51
Next step we'll see how to improve upon this.
7:54
(upbeat music)