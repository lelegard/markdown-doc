# Build a Toble of Contents in a markdown file

The Python script in this project builds a table of contents in a markdown file.

In the input markdown file, when a line starts with `**Contents:**`, it marks
the start of a table of content. The input file is then modified. A table of
content is inserted immediately after this marker line. If a table of content
already existed and is different from the new one, it is replaced.

This script is based on the markdown format as used on GitHub.

Usage: markdown-toc [options] md-file ...

Options:
- `-h` : print this help text
- `-o` : only output table of content, don't update input files
- `-t 'string'` : existing ToC header string, default: `**Contents:**`.

Example: Consider the following markdown file:
~~~
# Main title

Introduction....

**Contents:**

## Topic 1
Text...
### Subtopic 1.1
Text...
### Subtopic 1.2
Text...

## Topic 2
Text...
### Subtopic 2.1
Text...
~~~

After running the command `markdown-toc example.md`, the file is updated as follow:
~~~
# Main title

Introduction....

**Contents:**

* [Topic 1](#topic-1)
  * [Subtopic 1.1](#subtopic-11)
  * [Subtopic 1.2](#subtopic-12)
* [Topic 2](#topic-2)
  * [Subtopic 2.1](#subtopic-21)

## Topic 1
Text...
### Subtopic 1.1
Text...
### Subtopic 1.2
Text...

## Topic 2
Text...
### Subtopic 2.1
Text...
~~~
