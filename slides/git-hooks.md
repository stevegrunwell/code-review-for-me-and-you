### Git hooks

* <!-- .element: class="fragment" --> Enable you to execute scripts throughout the Git lifecycle
* <!-- .element: class="fragment" --> Not stored within the repo!
* <!-- .element: class="fragment" --> Analyze code before committing, perform actions ahead of a `git push`

Note:

* Scripts that can be executed throughout Git lifecycle
* Not stored in the repo by default, but can easily be distributed
* Things like automatically running PHP_Codesniffer pre-commit, updating dependencies on git pull, or running tests ahead of a git push
