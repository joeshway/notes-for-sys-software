In every git project folder there is a hidden folder that is .git. This folder has the entire history of commits, trees, blobs, and tags. 
The way that it stores everything is a bit interesting. Each object in the .git folder is just a compressed file. A **blob** is just some collection 
of bits. They are generally files but they don’t have to be. The name of these objects is actually an **SHA1** hash of the contents with the first two 
characters of the hash removed. The first two characters become the objects parent directory in the .git folder. This is just so there are not a bunch 
of files floating around in the root .git folder. Git calls this "content-addressable", in other words, names based on their contents.


A **Commit** object is a bit more complicated. It is still named in the same way but its contents are much different. A commit represents a 
complete version of the code being worked on. The first line will have a hash, that is the object containing the state of the **tree**. A tree is a 
manifest of files and folders. It represents the file structure at the time of the commit. Sub folders of the tree are just pointers to other tree 
objects. This continues until there are no more subfolders. As the article put it, "recursion!". The next line is a hash containing a pointer to the 
previous commit. The rest of the lines have user information such as author and committer user.


Say there are thousands of objects in a database. Finding the hash to the last commit may become difficult without writing it down. This is 
where **branches** come in. A branch is the hash to the last commit. When executing a Git command it looks at the file at *.git/HEAD* to see what the 
working directory is supposed to be. The HEAD file either in a branch name that has the hash to the last commit, or it is a commit object, which 
would be called a detached head. It then opens the commit object to find all of the trees, blobs, and parents all the way down.







#References
###Git Is Simpler Than You Think
http://nfarina.com/post/9868516270/git-is-simpler
