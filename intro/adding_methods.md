can you please evaluate the the following and provide scripts / snippets to learn the material? 

0:04
- [Instructor] Next, let's talk more about methods
0:06
in our classes.
0:08
As far as some terminology, we call something
0:10
a method when it is a function as a property
0:13
on an object,
0:14
and more specifically,
0:16
when we add methods to classes
0:18
in the way that we've seen so far,
0:20
we refer to them as instance methods.
0:22
Instance meaning the specific instances
0:25
of triangle.
0:27
So this display method has access
0:30
to the specific data from the instance of triangle
0:34
it is called on.
0:36
And we can access the instance using the key word this.
0:39
This is going to refer to whichever triangle
0:43
we're calling it on.
0:44
Essentially whatever's to the left
0:45
of the method column of the period,
0:48
so T one dot display,
0:50
instead of display, this is the T one triangle object.
0:54
If we had another triangle, my try dot display,
0:58
this would refer to my try.
1:02
And ABC would be the corresponding values on my try.
1:07
So let's add another method.
1:09
This one we'll call get area,
1:13
and the way our triangle is defined,
1:15
ugh, another geometry lesson very quickly.
1:17
This is not necessarily a right triangle
1:20
where there's a hypotenuse and an A and a B,
1:22
this is a generic three-sided triangle
1:26
and so we can't use that simple A times B
1:29
divided by two, base times height.
1:32
So we've got another formula,
1:34
this is called Heron's theorem, or Heron's formula.
1:38
It doesn't matter.
1:39
The point is, we're adding a method.
1:40
And this method uses this.
1:42
I'm using destructuring so we don't have to constantly
1:45
write this dot A, this dot B, this dot C, this dot A.
1:48
It'd be a lot of thises.
1:50
But if we looked at A, B, and C,
1:52
destructured from this,
1:54
it's the same thing we're doing here.
1:55
This dot A, B, and C.
1:57
Okay, so get area is defined,
2:00
and we can execute it on T one,
2:02
which I've already created.
2:03
T one dot get area.
2:05
We get six.
2:07
So that works great, we can make another triangle.
2:10
Let's do T two.
2:12
And we'll do some non-right triangle numbers.
2:15
So this is a nice easy right triangle.
2:17
I have no idea if this will be a valid triangle.
2:20
Let's do five, nine, and 10.
2:24
Let's look at T two dot get area.
2:27
Okay, kind of an ugly area,
2:28
but apparently that's what it is.
2:32
So that's just another example of defining a method.
2:35
These methods we create can accept arguments.
2:39
This one doesn't, this one doesn't, this one doesn't.
2:41
But they can, there's nothing wrong with this,
2:43
they're just any old methods.
2:45
Also, they can return values,
2:47
like we're doing here.
2:48
Instead of console dot logging,
2:49
which is really not that common.
2:51
It's just easy to show you something with a console dot log.
2:53
But more typically, we would return a value,
2:57
except in the constructor, as we saw in the previous video.
3:00
We don't wanna return something from here.
3:02
And we can also call other methods from within
3:05
a method in a class.
3:06
For example, let's define a method called is big.
3:10
And is big we'll call get area, and if get area
3:14
is greater than 50, neither of these triangles
3:17
have an area greater than 50, but let's say
3:20
if greater than 50, return that value.
3:23
Return true or false.
3:25
I'm doing one thing wrong here,
3:27
which is I'm not calling this dot get area.
3:30
If I simply reference get area,
3:32
we're not gonna have a good time.
3:34
Let's try it.
3:35
T one dot is big.
3:38
Get area is not defined.
3:41
It doesn't know about get area,
3:43
it knows about this dot get area.
3:46
This refers to T one or T two, the specific instance.
3:50
And that's very important.
3:52
Now we get false.
3:54
Now if we made a third triangle,
3:55
and this one we knew is very large,
3:58
let's just do T one but multiply each side by 10.
4:02
So 30, 40, and 50.
4:03
If we call T three dot get area, okay,
4:08
definitely larger than 50.
4:09
Now if we do T three dot is big, it's true.
4:13
So for that one instance, T three dot is big,
4:17
this refers to T three, so this dot get area
4:21
is calling T three dot get area.
4:23
It's not actually using the word T three
4:26
or that identifier, it's what this refers to,
4:28
this same object.
4:30
It's a reference to this object right here.
4:33
And then that returns a value, which is 600,
4:36
which is definitely larger than 50.
4:38
So we get true.
4:40
And that's pretty much all there is to methods in a class.
4:42
You can define a method anywhere using this syntax
4:45
while inside the class.
4:47
Typically, we put the constructor up top
4:49
just to make it clear, but it does not have to go there,
4:52
it's just the first thing that runs automatically.
4:54
It makes sense that it should go up top.
4:56
And then we have other methods,
4:58
and we can pass in arguments.
4:59
We haven't written one
5:00
where we are passing in an argument, but we could.
5:03
And then we can return values as well.
5:05
And to call other methods and to access other properties
5:09
on the instance, we use the keyword this.
5:12
This dot A, this dot B, this dot C.
5:14
Or a method, like this dot get area,
5:17
which I'm calling from within a different method.
5:20
Without the this, things go wrong.
5:23
This refers to the instance of the triangle class.
5:26
All right.
5:28
(upbeat music)