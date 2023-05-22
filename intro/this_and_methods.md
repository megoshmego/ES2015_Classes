can you please evaluate the the following and provide scripts / snippets to learn the material? 

Instructor] We've seen that we can put functions
0:05
in an object.
0:06
We can also put data in an object,
0:09
and they don't have to exist in the siloed walls.
0:12
They don't have to have horse blinders on (laughs)
0:14
where they can't see the other members of the object.
0:17
We can create objects where functions, or methods,
0:20
can interact with other properties,
0:22
other data on the object.
0:24
They could even call other functions on the object.
0:27
The secret is the keyword "this".
0:30
So we're gonna come back and spend a lot more time
0:32
with that weird keyword "this" in JavaScript,
0:35
but this will be a quick overview of one scenario,
0:38
one use case, or behavior of the keyword "this".
0:41
Okay, so we have two functions here that have to do
0:44
with right triangles.
0:46
We don't need to go into too much geometry here.
0:48
If you never had geometry, or you don't remember it,
0:51
a right triangle is a triangle where one angle is 90 degrees
0:54
and there are two shorter sides,
0:56
and then one extra long side called the hypotenuse,
0:59
and to figure out the hypotenuse,
1:01
we can take a and b, so the shorter sides,
1:05
square them, add them together, and then square root that.
1:08
It's a whole a squared plus b squared equals c squared.
1:10
So we have a function that will calculate
1:13
a squared plus b squared, then take the square root of that,
1:16
and if we call it "gethypotenuse",
1:19
a standard, uh, right triangle, an easy one,
1:21
has sides of three, four and five.
1:23
I think there's another easy one which is nine and 12,
1:27
which gives us 15.
1:28
Most other numbers, if you plug them in,
1:30
you'll get nasty numbers like this.
1:34
Generally, square root does not give you a nice number.
1:37
Anyway, so that's one function.
1:39
We have another function called "getarea",
1:41
and to get the area of a right triangle,
1:43
we take the two sides, a and b,
1:44
multiply them, divide by two.
1:46
It's also known as base x height divided by two.
1:50
Again, the math doesn't matter,
1:51
but if you find the area for three, four,
1:54
this triangle here, the hypotenuse is five.
1:57
The area would be six square whatever the units are.
2:01
Okay (laughs) so that is our geometry lesson.
2:04
Not a very good one.
2:05
We have these two functions,
2:06
and they both require us to pass in
2:09
the values for our triangle.
2:10
So if we were working with a triangle...
2:12
Let's say we're actually drawing it on the screen.
2:15
If you're familiar with the Canvas API,
2:17
that would be one way of doing it.
2:18
If you've never heard of it, just know that there is a way
2:20
to draw a triangle in the browser,
2:22
and I wanna keep track of the sides of the triangle,
2:24
so I need to have three and four stored somewhere.
2:27
I could do this, const side1 equals four.
2:31
Const side2 equals three, or the other way around,
2:36
and then I would need to pass these values in.
2:39
If I need the side three, I could do
2:42
"gethypotenuse" of side1, side2,
2:46
and if we look at side three, it's five.
2:50
If I want to get the area,
2:52
I could do const area equals "getarea"
2:55
of side1, side2, area.
3:01
Yeah, this isn't too bad. We pass the values in every time.
3:05
If I wanted to change one of those values,
3:07
like my triangle sides change,
3:09
we're displaying a different triangle,
3:11
or maybe instead of four, it's five here.
3:14
Well, I'm using const, so, uh,
3:16
I wouldn't be able to do that in my code. (laughs)
3:18
If I used let instead, I could update the side,
3:21
and then to calculate the new hypotenuse,
3:24
I would need to pass it in again.
3:25
So if I said side1 is now equal to nine.
3:29
Side2 is now equal to 12,
3:31
then I would need to do "gethypotenuse" again,
3:34
and pass in nine and 12.
3:35
I have to keep track of these values myself.
3:38
They're scattered about.
3:39
I have to pass them in as arguments to every function call,
3:42
and we can have a lot more, other than these two functions,
3:45
"gethypotenuse" and "getarea".
3:47
We could have a function called, um...
3:49
Well, geez. I don't know.
3:50
Change color of triangle, if we're showing it on the screen,
3:53
or animate triangle,
3:54
and we would need to pass in
3:55
potentially a and b, the two sides over and over and over.
3:59
So what we can do instead is create an object,
4:03
and this object will have a and b as values on the object,
4:07
as well as properties that are methods,
4:10
"gethypotenuse" and "getarea",
4:12
and that would look something like this.
4:14
So we have an object.
4:16
We have a as a property, b as a property.
4:18
We have the two methods, "getarea" and "gethypotenuse",
4:22
and then the magic of it all is the "this" keyword.
4:25
So these functions don't have any arguments.
4:28
We don't pass in a and b.
4:30
Instead, we will look them up on the object.
4:33
So in this object you see here,
4:35
"this" is going to refer to "this object".
4:39
This object right here. My parent object.
4:42
The thing that the function is contained in.
4:45
This is actually a lot more nuanced than that,
4:47
and there are other situations where it behaves differently.
4:50
It's something that we have to talk about,
4:52
and we'll have a couple videos on it later,
4:54
so this is not supposed to be
4:55
a comprehensive intro to "this".
4:57
It's only one scenario.
4:59
But in this scenario,
5:00
"this.a" will retrieve a from this object.
5:05
"This.b" retrieves b. So we can test it out.
5:09
We can make our triangle const, uh,
5:11
let's call that righttriangle, because that's what it is.
5:15
These formulas don't work for every triangle,
5:17
as far as I remember at least.
5:18
We can set different properties, like a, which will be...
5:22
Let's go with nine.
5:24
B will be 12,
5:26
and then we have "gethypotenuse" and "getarea".
5:29
We could use this syntax. "getarea:",
5:34
and then we write our function,
5:36
and our function will have no arguments,
5:39
and will instead retrieve a and b from this object,
5:42
and if you just copy this here.
5:45
We need to update it to be "this.a" and "this.b".
5:48
Let's see if it works. So "righttriangle" is an object.
5:52
If I call "righttriangle.getarea", empty parens.
5:58
I don't pass anything in, we get 54 for this triangle.
6:02
We'll have to assume that's right.
6:03
Um, I guess we could call the original "getarea",
6:06
and pass in nine and 12.
6:08
This function here, we also get 54. Cool.
6:12
So we could add in "gethypotenuse",
6:15
um, let's just copy the whole thing over,
6:17
and then update it.
6:19
So "gethypotenuse:function" a, b. Get rid of that.
6:25
No arguments.
6:26
Now, we just update it to use "this.a" and "this.b",
6:32
and if you're unsure what this is,
6:34
what if we make a new function on here, a new property,
6:36
called "printthis", which will be a function,
6:41
and it simply console.log's this,
6:45
and then you need to add a comma, okay?
6:48
Try it now. Let's call "righttriangle.printthis".
6:54
This is an object,
6:56
specifically it is this object right here.
6:59
So "this.a" gives us a, "this.b" gives us b.
7:02
I could even call "printthis"
7:04
from within one of these other functions if I wanted to.
7:07
Inside of "gethypotenuse", I could call "this.printthis".
7:13
So I'm calling the "printthis" method on this entire object
7:18
from within a different method.
7:20
So now, if we call "righttriangle.gethypotenuse",
7:25
we get our console.log of this, the entire object.
7:29
This method is called, and we get 15,
7:32
which is hopefully the correct answer.
7:33
It's what we got earlier with our standalone function.
7:37
Okay, a couple notes about the keyword "this"
7:39
very briefly.
7:41
We could rewrite these functions
7:42
with the different syntax we've seen
7:44
to add methods to objects,
7:46
where you could write it like this.
7:48
"printthis", "getarea" and "gethypotenuse".
7:55
It's the exact same thing.
7:56
We just don't have to use the colon.
7:58
We don't have to write the function keyword.
8:00
If I run my code again, I still get the same output.
8:03
What we cannot do is use an arrow function.
8:07
Technically we can.
8:08
There's now law or rule against
8:10
using arrow functions in objects as methods,
8:13
but the keyword "this" will behave differently.
8:16
That's all that I'll say about it.
8:17
If we updated "printthis" to be an arrow function,
8:20
like this right here, it's valid.
8:23
I can call "printthis", but if I try it,
8:25
"righttriangle.printthis", we get a different this,
8:30
and that's all I'll say about it for now,
8:32
because I don't wanna go too in depth with it.
8:34
We will come back to it. Just notice it's different.
8:37
It's referring to the window object,
8:39
so there is no "this.a".
8:41
If I wanted to print "this.a", we get undefined.
8:45
If I change this back to a regular function,
8:48
get rid of that arrow, and try it again.
8:52
Same function call, gives me nine. So a big difference.
8:56
And with that said, I think this is a good place to stop.
8:59
We have made one object, one triangle,
9:02
where we store a and b, and we have different methods,
9:05
and I can update those properties if I wanted to,
9:08
and I can say "righttriangle.gethypotenuse"...
9:11
Oh. I gotta get rid of "this.printthis",
9:14
because I removed that method.
9:16
Try that again. (laughs)
9:18
I get hypotenuse,
9:19
and then I can change right triangle's values,
9:22
like, "righttriangle.a" is now equaled to three.
9:25
"righttriangle.b" is now equal to four,
9:29
and I call "gethypotenuse" again.
9:31
We get a different value.
9:33
So just a different organizational structure,
9:36
rather than having standalone functions
9:38
where we save variables and pass them around
9:41
to keep track of our triangle.
9:42
Here, it's all grouped in one place.
9:44
We have functionality and data. But there's a problem.
9:49
This isn't really reusable.
9:51
How do I make another triangle?
9:52
I guess we could clone this object
9:56
every time we needed a new one,
9:57
uh, but then we would be starting out with nine and 12
10:00
for every single triangle.
10:02
Is there a better way of doing it? Yes. (laughs)
10:04
The answer is yes, and we're gonna learn that next.
10:07
So we'll see how to make a repeatable pattern,
10:09
so we can make multiple triangles, like a triangle factory.
10:12
That's coming up next.