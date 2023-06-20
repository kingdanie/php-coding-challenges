# Create a class handler
Your task is to create a simple command handler whose job is to update an
existing blog post, dispatch an event if the operation succeeds, and
properly handle exceptions.
You don't have to worry about the rest of the application. Also, all necessary
classes will be imported out of the box, so you don't need to think about
adding any "use" statements.
Requirements
Your command handler must:
1. Create a BlogPost object based on the data provided in the
UpdatePost command.
2. Update the post using the PostUpdater service provided in the handler
constructor.
Dispatch the PostUpdated event with a proper post ID using the
EventDispatcher service, assuming no exceptions were thrown while
performing the operations described in points 1 and 2 above.
Handle an exceptions that occur, depending on the exception class.
The following table shows how exceptions should be handled depending on
their class:

| Exception name                      | Way of handling                     |
| ----------------------------------- | ----------------------------------: |
| PostDoesNotExist                    | let it bubble out of the handler    |
| TitleTooLong                        | let it bubble out of the handler    |
| PostBlockedForEditing               | catch it and throw FailedToUpdatePost instead |
| any other throwable                 | catch it and throw FailedToUpdatePost instead |

Assumptions

The initial handler looks like this:

```php

<?php

declare(strict_types=1);

namespace App;

class UpdatePostHandler
{
    private EventDispatcher $eventDispatcher;
    private PostUpdater $postUpdater;

    public function __construct(EventDispatcher $eventDispatcher, PostUpdater $postUpdater)
    {
        $this->eventDispatcher = $eventDispatcher;
        $this->postUpdater = $postUpdater;
    }

    /**
     * @throws FailedToUpdatePost
     * @throws PostDoesNotExist
     * @throws TitleTooLong
     **/
    public function handle(UpdatePost $command): void
    {
        //implement the handler here, do not change anything outside of this method's body!
    }
}

```


The UpdatePost object used as an argument for the handle method is defined as follows:

```php
class UpdatePost
{
public function __construct (int $postId, int SuserId, string $title,
string content) {//.
..f;
public function getPostId(): int (//...}:
public function getUserId(): int {//.
.:
public function getTitle(): string {//.
public function getContent(): string {//...};
The handler has access to two internal services:
a post updater;
an event dispatcher.
They will be used to perform all necessary operations within the handler.
Using the PostUpdater
This service is responsible for updating the blog post. It implements the following interface:
interface PostUpdater
{
/**
* @throws PostDoesNotExist
* @throws PostBlockedForEditing
* @throws \Throwable
*/
public function update (BlogPost $post): void;
}
```

For the sake of this task, there is only a single class implementing the event: PostUpdated. Its constructor is
shown below:

```php
class PostUpdated implements Event
{
public function
__construct (int SpostId, int SuserId)
}
```

* For the sake of clarity, you can safely assume that:
All classes mentioned in the task are in the same directory; there is no need to include them.
You do not have to write your own implementations of any class provided here; please assume they
already exist.
No exception/error will be thrown within this task unless it is mentioned in the proper class description.
Hints
* Look closely at the object contracts presented in the Assumptions section for method arguments and
possible throwables.

Think carefully about what error/exception you need to catch (or not), and in what order.
If the tests throw errors concerning not imported classes, make sure to check for possible spelling
mistakes. There is no need of writing any use statements in this task.
You will be using PHP 8.0 in this task.


 

