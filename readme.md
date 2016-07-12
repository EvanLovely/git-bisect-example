# Git Bisect Example

## Setup

    npm install
    npm start

## Usage

Here's how to use `git bisect` to find out when the header got an ugly red color to it's border:

- `git bisect start` - Starts a session; now it just needs a `good` and a `bad` to search between.
- `git bisect bad` - Since the current commit has an ugly red color for the header border, we'll tell it that this is `bad`.
- `git checkout 8529499` - We check this revision out and look at it to see if it looks good; it does, so we:
- `git bisect good` - Now that `git bisect` has two commits to search between, it will check out another commit half way between `good` and `bad` for us. 
- We look at the state of our page that `git bisect` checked out for us and enter either: `git bisect good` if no ugly red color or `git bisect bad` if there's an ugly red color.
- Eventually, it tells us the exact commit where the ugly red color got added.
- Once we're done, we run `git bisect reset` to get back to `HEAD` where we can fix it.

## Reference

- [`git bisect` docs](https://git-scm.com/docs/git-bisect)
- [Stack Overflow HowTo](http://stackoverflow.com/questions/4713088/how-to-use-git-bisect)
- [Blog post tutorial](http://www.metaltoad.com/blog/beginners-guide-git-bisect-process-elimination)