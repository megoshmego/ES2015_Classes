can you please evaluate the the following and provide scripts / snippets to learn the material? 


- [Instructor] Welcome back, we've seen how to define
0:07
a class and we've seen that we can add properties
0:09
on specific instances of the class.
0:13
Once we call new triangle that gives us an object,
0:15
it has access to these methods.
0:17
And then we can one at a time manually add in pieces of data
0:21
like a and b for the side to the triangle,
0:24
this is not ideal.
0:25
It would be much easier and much better to be able
0:27
to pass in data.
0:29
Kind of like, when we call new set like this, we can make
0:32
an empty set or we can pass in some data to that set
0:37
an iterable like this string, I don't know, butterfly,
0:42
and then it creates a set using that data.
0:45
How could we do that with our triangles?
0:47
How can we pass in data when we call new triangle?
0:51
Well, we can definitely pass it in, we can put whatever
0:53
we want in here, I could do three comma four,
0:56
but where does it go?
0:58
Where do we have access to it in this class?
1:00
In this pattern we're defining, how can we write code
1:04
that will accept these values and then add
1:07
them to the instance?
1:09
Well, we do this using constructors.
1:12
There is a special method that we need to add to our class
1:16
with the name constructor.
1:18
It is special because it's automatically called for us.
1:22
We never call it ourselves like we would call get area
1:25
or display, all that we do is create a new triangle
1:28
using new triangle and then the constructor
1:32
is automatically run.
1:34
So, if we wanted to try it, if we just put a constructor
1:37
in here usually it goes to the top, it does not have to,
1:40
and in here, I'll just say console.log. you made
1:44
a new triangle.
1:46
If we try making a new triangle, like this new triangle,
1:51
you made a new triangle, this method called constructor
1:55
was automatically run, it does have to be named constructor.
1:59
Notice how VS Code highlights it in purple like it does
2:02
for class versus every other method, greet and display
2:06
has a different color.
2:07
That's just a way of telling you that this is a significant
2:11
or a special keyword in JavaScript constructor.
2:15
So, this is kind of cool, I guess it's automatically called
2:18
but the whole point of this was to be able to pass in data,
2:22
when we make a new triangle like three four, five,
2:25
that should make us a new triangle with sides of a, b and c,
2:28
three, four and five.
2:30
So, if we write our constructor function to expect three
2:34
values our triangle for now, we'll just be any triangle
2:38
that has three sides, we were doing a right triangle
2:41
earlier, we'll come back to that.
2:43
We're just gonna make a simple triangle, any three sides.
2:46
Okay, if we try this and inside we console.log
2:51
a, b and c, you'll see that the data does make it through.
2:55
When I call new triangle, let's do five, six, seven
3:00
that's what we get printed out, those parameters we define
3:03
here, are accessible in the constructor function.
3:07
In fact, that's the whole point that constructor exists
3:10
for us to accept data when a new triangle is instantiated
3:14
or created with new triangle.
3:16
And then we can take that data that was passed in here
3:20
and do something with it, usually added onto the specific
3:24
instance and the way that we referenced that instance,
3:27
like we've already seen is using the, this keyword.
3:31
So, to assign a, b and c to the specific object,
3:36
the new triangle we're making, we call this.a instead
3:40
of equal to a, this.b equals b, this.c equals c.
3:45
So, we can do that here, you don't have to use the same
3:47
name, it's pretty standard to do that,
3:50
but we could also do this.side3 equals c.
3:54
There's nothing wrong with that, you just need to know
3:56
that property is now called side three which I will change
4:00
shortly, if we run it and then make a new triangle,
4:03
again, five, six, and seven.
4:06
Now we can see this triangle has specific properties on it.
4:10
Just like what we did earlier, when we called new triangle
4:14
and then manually added properties one at a time,
4:18
const t equals and then t.a equals five,
4:23
t.b equals six, t.side3 equals seven.
4:29
We're accomplishing the same thing but we don't have
4:31
to write all of that stuff, because if we're doing
4:34
this for every single triangle we make, we just move
4:37
it into the constructor.
4:38
This is automatically run for us, when we make
4:41
a new triangle, we pass in those three values
4:44
and they are set as specific properties on the instance.
4:47
So, if I try making another new triangle,
4:50
I'll do a, let's save this one to a variable const t1,
4:55
and then do another triangle, we'll be very creative here,
4:58
t2 equals, I have no idea if this is a valid triangle,
5:04
nine, 20 and 50,
5:06
we look at t1, it has its own a, b and side 3,
5:11
and we look at t2, it has its own a, b and side 3.
5:16
and I can still call greet on both of them,
5:19
it has nothing to do with a, b and side 3,
5:22
but we do have access to those methods.
5:24
But most importantly, if I call display,
5:28
this method is looking for an a property and a b property
5:32
on the specific instance of triangle.
5:35
So we get triangle with sides of five and six.
5:38
We're not using side three because our method
5:40
doesn't care about it.
5:42
And if we did t2.display,
5:45
triangle with sides of nine and 20.
5:48
So in this constructor, we can do a whole bunch of things.
5:51
Typically, we're adding properties to the instance using
5:55
this, we're adding data that was passed in
5:58
onto the specific triangle objects that are created.
6:01
a and b and side 3 are properties, not on the class
6:05
but on these objects we're creating like t1 and t2.
6:09
This is only the pattern or the template, and this is really
6:13
a placeholder for whichever objects we're creating.
6:16
So we can add properties, that's a really common thing
6:19
to do in the constructor.
6:20
Another common thing is to validate the data.
6:23
So validating data would be something like this,
6:26
maybe for our triangle, checking to make sure the numbers
6:29
that have been passed in are actually valid numbers,
6:31
they're not negative numbers for a side and they're not
6:35
strings, are not a Boolean, they are numbers.
6:38
So we could do something like that, why don't we change
6:41
side 3 to now be c to keep with our pattern.
6:44
I just wanted to show you that this name does not matter.
6:47
It has no connection to the name of the parameter,
6:50
it's like any other function.
6:52
These are purely defined by order, they're filled in order.
6:56
So you pass three things and the third one is c,
6:58
if you only pass two the last one will be b, okay.
7:02
So let's update our display method to also display side c.
7:08
So we have sides of this.a, this.b and this.c.
7:14
Okay, we'll try that.
7:17
I'll try making a new triangle again, we'll just go
7:19
with a t2, we call t2.display.
7:25
And we get triangle with sides of nine, 20 and 50.
7:28
Next, let's add some simple validation, pretty much
7:31
what I showed on this slide to make sure that the sides
7:35
a, b and c are numbers and they're greater than zero.
7:39
To help us out, we can use a method called Number.isFinite
7:45
and you pass number into it or some value.
7:48
If we do a number, we'll get true, it could be a decimal.
7:52
It can be a negative number, but as soon as you pass in
7:55
something that is not a number, we get false.
7:58
Even if it's a string that looks like a number,
8:00
if it's a Boolean, we get false.
8:03
Any other thing that is not a number it's an easy way
8:06
to check if something is a number, so let's use that.
8:08
And we could just start by validating a,
8:11
so if Number.is Finite of a,
8:16
and let's also check first if it's not a number,
8:20
so if a is not a valid number, or if a is less than
8:24
or equal to zero, we don't want negative sides.
8:28
Negative two, as a length for a side of a triangle,
8:31
we also don't want zero, no side.
8:34
So we'll check, if it's less than or equal to zero,
8:37
or if it's not a number, if that's the case,
8:40
what should we do?
8:42
You might think if we could just return something
8:45
like return, not a valid side,
8:49
or false or undefined or not a number, return something.
8:53
However, you never want to return a value
8:56
from a constructor.
8:57
It's not something that you want to do
8:59
because of the way constructors work.
9:01
We're never executing this function on our own.
9:04
We're not calling constructor like this, we're not doing,
9:07
I don't know, triangle.constructor.
9:10
Instead, it's called for us when we execute new triangle.
9:15
So, if we try returning something in here, it will stop
9:18
the execution of the constructor but it doesn't stop
9:22
the new triangle from being made.
9:25
So, it stops this code from running but we still
9:27
will get a new Triangle.
9:28
If I try it here, const my triangle equals
9:33
new triangle and let's pass in a negative number,
9:37
negative three, four, and five.
9:41
Okay, so I don't see not a valid side.
9:45
And we can verify this code is running just to make
9:48
sure console.log invalid side.
9:52
So we should see this prints out as a side effect
9:55
even though we're not getting that return value.
9:57
If we try it, okay, it does print out but if we look
10:00
at my triangle, it is a triangle, we made a new object.
10:05
It has those methods, display and greet, but we never
10:08
assigned a, b and c.
10:09
So this is not something you wanna do in a constructor.
10:12
You don't want to return, we're not directly calling it.
10:15
So, the return value never makes it back to our variable.
10:19
Instead, it stops the execution of the constructor
10:22
but it can't stop the greater machine.
10:24
It can't stop the object from being created,
10:27
the new triangle.
10:29
So, what you would do if you wanted to validate,
10:32
is to throw a new error which looks like this,
10:35
throw new error and we can pass in a string,
10:39
like sides must be positive numbers.
10:46
Now, if we try this,
10:49
we now get an error, and that stops everything else,
10:52
that, it crashes everything that has to do
10:55
with creating a new triangle.
10:57
So if we look at myTri, there is no value.
11:01
It was never defined because we threw an error.
11:04
If you're not very familiar with throwing errors
11:06
that's something that we'll talk more about.
11:08
For now, this is all you need to know.
11:11
Throw new error, take a look,
11:13
the new keyword showing up once again, if we just call
11:16
new error here, we pass in something,
11:21
it makes us this error object.
11:24
And if we try it again, and this time we throw the error,
11:27
this is what we see.
11:29
The key thing to remember is that you don't want to return
11:31
a value from your constructor, it will get lost
11:34
in the abyss, you won't be able to capture
11:36
that return value.
11:37
So if you need to validate something and stop execution,
11:41
you can throw an error.
11:43
And later on, you'll see how you can catch an error
11:46
or how to prevent this disaster from happening
11:48
where everything freaks out and your code stops.
11:50
We'll see solutions.
11:52
Let's refer to this, so that we don't have to write
11:55
this exact same code three times for b and c.
12:00
This does work but it's a bit lengthy.
12:03
Let's just verify that, it should be c,
12:06
or try and make a new triangle, this time with sides
12:09
of three, four and nothing, we get invalid side.
12:14
We can get rid of those console.logs anyway,
12:17
for throwing an error.
12:19
If we instead pass in one number, same thing, we don't pass
12:24
in anything, we're not giving very detailed feedback.
12:27
We could have a different error if an argument was missing
12:31
versus if an argument was negative if it's not a number,
12:35
but this is simple enough.
12:36
The last thing I would probably do is rewrite this using
12:39
a simple loop.
12:41
We can loop over the arguments here.
12:44
I would probably just do this, for let side of
12:48
and then I'll just put a, b and c in a new array like that.
12:53
And then I'll copy this up, paste it and change a,
12:57
to be our side variable from the loop, and then get rid
13:01
of all of this.
13:04
So this is not really essential to understanding classes,
13:07
just refactoring a bit.
13:09
Let's verify that it works, new triangle empty, we get
13:11
our same error, if I do a three, four and the string
13:15
five same thing, okay.
13:18
So what we saw here in this video, it's been a bit long.
13:21
I know, I apologize for that.
13:23
We saw constructors, when you make a class, we add
13:27
a constructor, we never call it ourself.
13:30
Instead when we create a new triangle, when we instantiate
13:33
an object from this class, from this blueprint,
13:36
the constructor is automatically called and whatever values
13:39
we pass in are added as arguments, well, they're not added,
13:43
they are passed into the constructor function.
13:45
And we have access to them, we can do things like validate.
13:48
And then most importantly we can add those values
13:51
as properties on this.
13:54
And remember this refers to the specific instance
13:57
in our case of triangle.
13:58
If this was instead a button class, a color class,
14:02
a dog class, this refers to the specific instance
14:05
the object we are instantiating based upon this template.
14:10
Alright, it's a lot.
14:11
Let's take a break and then, well, you can take a break.
14:14
I'll see you in like 10 seconds in the next video.
14:17
