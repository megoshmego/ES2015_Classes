can you please evaluate the the following and provide scripts / snippets to learn the material? 

0:09
using object literal syntax with those curly braces.
0:12
You may come across this term.
0:14
POJO actually never heard anyone say it out loud.
0:17
I don't know if it's POJO or PAJO, whatever it is,
0:21
plain old JavaScript object.
0:23
Here's an example.
0:24
Here's another way of making an object, an empty object,
0:27
and then we can set properties on that object manually
0:30
one at a time using either the dots and techs
0:33
or the square brackets.
0:35
Now there is a significant difference.
0:37
If we come over here, if we have some variable
0:40
we'll call this a, how about color and set it to teal.
0:44
If I make myself a new object
0:46
I'll just call this OBJ curly braces, it's an empty object.
0:50
If I wanna add a property, using this color,
0:55
if I do OBJ dot color and set that equal to
0:58
how about a hex code, I'm just making this one up.
1:00
I have no idea what color this will actually be.
1:03
It's not too far from teal,
1:05
kind of, we've added a new property
1:08
but the property has the key of color.
1:12
If I use the square brackets instead
1:14
OBJ of color equals the same thing.
1:18
We end up with this being evaluated
1:21
and turned into the string teal.
1:25
If we double check that, there we go.
1:27
So we now have two properties color
1:29
the literal word, the identifier we wrote here.
1:32
And then here, we're actually evaluating this.
1:35
And you know, we could do other things
1:37
1+4-2x8.
1:41
And what do we get?
1:43
It's evaluated to negative 11.
1:45
That is our key.
1:46
If you ever need the keys
1:48
from an object, we have a keys method.
1:50
We have a values method, and we have an entries method.
1:53
If you ever need to get the keys
1:54
or the values from a particular object
1:57
we have a special method called Objects capital O Object,
2:02
not OBJ,
2:04
our instance dot keys.
2:06
If you try that, it does not exist.
2:08
We have to call Object dot keys
2:10
and then pass in our particular object.
2:13
That gives us an array containing the keys.
2:16
We have values as well.
2:19
I can get those values.
2:20
If I wanted to iterate over the values,
2:22
I can iterate over the keys or,
2:24
we have another method on this object,
2:27
mysterious capital O object called entries.
2:31
And this will give me an array, where each element is a pair
2:35
a key value pair.
2:37
And I could use that to iterate
2:38
if I needed the key and the value,
2:40
for, let and we'll come back to the variable name
2:45
of Object.entries
2:48
of our Object OBJ,
2:50
that is going to give us an array that we iterate over
2:53
each time through if we just called this X.
2:56
X would be another array with two elements
2:59
and we can de-structure key and value like that.
3:03
And then console.logk, v.
3:09
We run that and there we go.
3:11
So that's an easy way to iterate relatively easy.
3:14
You just have to remember capital O Object.entries.
3:17
Next up, you should know
3:19
that if you try and access a property that does not exist
3:22
on an Object, you don't get an error.
3:23
You just get undefined by try and do obj.read or read
3:28
doesn't matter we get undefined.
3:31
Anytime you add a key to an Object,
3:33
it's turned into a string.
3:36
So it may not look like it's a string,
3:37
but it is indeed a string.
3:39
For example, what do we have here?
3:41
Negative 11, who is our key?
3:43
If we look at object,
3:45
when I access object of this string, negative 11
3:50
this is going to be turned into a string and already is.
3:52
And compared to the current properties
3:55
negative 11 as a string matches what I'm looking for.
3:59
If I leave off those quotes, I still get the same match
4:02
because this will be turned into a string.
4:04
This is already a string, even though it doesn't
4:06
display as a string and they're compared, we've got a match.
4:10
So all keys are stringified.
4:13
And I think that's good enough for a brief recap of Objects.
4:17
Key value pairs.
4:18
You set your key, you set it equal to a value.
4:21
You can update those values at any point, using that key.
4:24
There's a difference between the dots
4:25
and texts and the square brackets whatever's
4:27
in square brackets will be evaluated.
4:29
You could do math, I don't recommend it,
4:31
but you could, typically you would use this for variables
4:34
that you want to use to access something
4:36
in an object.
4:37
We can iterate.
4:38
Remember these methods that start
4:39
with capital O Object, keys, values, and entries.
4:43
And I think that's it.
4:44
All right, next, we're gonna talk about methods.
4:46
(upbeat music)