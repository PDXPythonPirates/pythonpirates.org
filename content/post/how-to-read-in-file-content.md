---
title: "How to Open and Read Files"
date: 2018-12-04
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

  1. Open the file using `open()`.  This returns a _**fileobject**_ for interaction.
  2. Read data from the fileobject using one of the methods described in the next section
  3. Close the fileobject.  You can do this explicitly by calling the method `fileobject.close()` or handle it automatically through the use of a `with` block.

`open()` is a built-in function and does not require `import` for use (similar to `print()` or `len()`).

You can find the documentation for `open` [here][open_docs]

> It's important that you always close a file when finished to avoid leaking system resources.
> The easiest way to do this is to open a file using a `with` block so the close is automatic.

## Three Ways to Read File Content

There are 3 common ways you can directly read from a **fileobject**:

* Call the method `fileobject.readlines()`.  This returns a list with each line of the file as an element in the list.
* Call the method `fileobject.read()`.  This returns the file contents as a single large string.
* Treat the fileobject as an *iterable* and loop over it using `for`.  This progresses through the file yielding one line with each iteration.

Examples of each:

{{< highlight python "linenos=table" >}}
# read file in as separate lines
# note: the second argument "r" is optional when opening 
#       a file for READ, and omitted in the next 2 examples
with open("scores.txt", "r") as fileobj:
    lines = fileobj.readlines()  # lines is a list
print(lines)
{{< /highlight >}}


{{< highlight python "linenos=table" >}}
# read file as one big string blob
with open("scores.txt") as fileobj:
    one_big_string = fileobj.read()
print(blob)
{{< /highlight >}}


{{< highlight python "linenos=table" >}}
# iterate over file lines
with open("scores.txt") as fileobj:
    for line in fileobj:
        print(line)
{{< /highlight >}}

Try out each of the above.  Be sure you create and execute your python file in the same directory as where you downloaded `scores.txt`.

Can you think of some pros and cons to each method?

## Example: Process Test Scores

Let's wrap up with a simple but complete example.  The sample file `scores.txt` contains student names and how they scored in a class.

Below is some code to read in the data and calculate a few stats about the scores:

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



[scores_download]: https://raw.githubusercontent.com/PDXPythonPirates/workshops/master/file-io/scores.txt
[open_docs]: https://docs.python.org/3/library/functions.html#open
