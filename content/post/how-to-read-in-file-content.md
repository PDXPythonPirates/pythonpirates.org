---
title: "How to Open and Read Files"
description: "A short tutorial that shows how to open and read text files using Python"
date: "2018-12-04"
lastmod: "2018-12-04"
#author: "Matt Phillips"
#author_github: "imattman"
header_image: "/img/keyboard-closeup.jpg"
---

# File I/O: Just Enough To Be Dangerous

Up to now most of the course exercises have you working with data that is embedded in the Python code.  While this is a good place to start, things become much more interesting when we can pull in data from an external source such as a file.

This is a quick introduction to opening and reading *text files* using only Python.  The goal is not to present deep and exhaustive coverage but instead give you just enough information to get you started.

### Download Sample File

The sample file referenced in this post is available for download to follow along: 
[scores.txt][scores_download]

## Open, Read, Close

The standard steps for reading a file are:

  1. Open the file using the function `open()`.  This returns a _**fileobject**_ for interaction.  
    The documentation for `open` is available [here][open_docs].
  2. Read data from the fileobject using one of the methods described in the next section.
  3. Close the fileobject.  You can do this explicitly by calling the method `fileobject.close()` or handle it automatically through the use of a `with` block.

> It's important that you always close a file when finished to avoid leaking system resources.
>
> The easiest way to do this is to open a file using a `with` block so the close is automatic.

## Three Ways to Read File Content

There are 3 common ways you can directly read from a **fileobject**:

* Call the method `fileobject.readlines()`.  This returns a list with each line of the file as an element in the list.
* Call the method `fileobject.read()`.  This returns the file contents as a single large string.
* Treat the fileobject as an *iterable* and loop over it using `for`.  This progresses through the file yielding one line with each iteration.

Can you think of some pros and cons to each method?

An example of each follows:

#### A List of Lines

This example does **not** use a `with` block so the file must be closed manually (line 4).

{{< highlight python "linenos=table" >}}
# read file in as separate lines
fileobj = open("scores.txt", "r") # the second argument is optional when "r"
lines = fileobj.readlines()
fileobj.close() # must manually close file

for line in lines:
    print(line)
{{< /highlight >}}

#### One Big String

This second example uses a `with` block which makes the call to `fileobj.close()` unnecessary since the file close is handled automatically.

When opening a file only to *read* and *not write*, the second argument to `open()` (`"r"`) can be omitted.

{{< highlight python "linenos=table" >}}
# read file as one big string blob
with open("scores.txt") as fileobj: # omit second arg "r"
    one_big_string = fileobj.read()
print(one_big_string)
{{< /highlight >}}

#### As an Iterable

This third example also uses a `with` block and omits the optional second argument to `open()`.

{{< highlight python "linenos=table" >}}
# loop over the fileobj directly
with open("scores.txt") as fileobj:
    for line in fileobj:
        print(line)
{{< /highlight >}}


## Example: Process Test Scores

Let's wrap up with a simple but complete example.  The sample file `scores.txt` contains student names and how they scored in a class.

Below is some code to read in the data and calculate a few stats about the scores.  You are encouraged to follow along by trying it out on your own computer.

Be sure you create and execute your python file in the same directory as where you downloaded `scores.txt`.

{{< highlight python "linenos=table" >}}
with open("scores.txt") as score_file:
    lines = score_file.readlines()

scores = []
for line in lines:
    # remove any leading/trailing whitespace and skip empty lines
    line = line.strip()
    if not line:
        continue

    # split on whitespace and unpack for multi-assignment
    student, score = line.split()
    # convert string value to int for computing stats later
    scores.append(int(score))

# make use of a few handy Python built-ins:  
# sum(), min(), max(), len()
print("count:  ", len(scores))
print("min:    ", min(scores))
print("max:    ", max(scores))
print("average:", sum(scores) / len(scores))
{{< /highlight >}}


# Future Topics

This only scratches the surface of working with I/O in Python.

Depending on group interest, possible topics to explore in the future include: working with structured data such as CSV and JSON;  dabbling with excel spreadsheets; and making web applications that serve data on a network.

Let us know in the MeetUp what you would like to dive into further.



[scores_download]: https://raw.githubusercontent.com/PDXPythonPirates/examples/master/file-io/scores.txt
[open_docs]: https://docs.python.org/3/library/functions.html#open
