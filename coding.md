## Class Name

A class name must represent an object in the domain.

In other words, you must use the terms used by end users, not by this project's developers.

Do not invent a name for the sake of programming.

However, you can switch the domain to low-level infrastructure concepts.

For example, let's say you need to make an HTTP request to send a message from one user to another.

In that case, you can create a class named `Http` to serve users.

Still, you must not invent a name outside the HTTP domain, such as `HttpUser`.

In other words, make a clear distinction between domains.

## Method Name

A method name must be either a noun or a verb.

If a method returns something, the name must be a noun.

For example, if an object `user` returns a name, the method name must be `name`, not `getName`.

If a method returns nothing (void or null), the name must be a verb.

For example, if an object `user` sends a message to another user, the method name must be `send`.

More importantly, use end-user terms to name methods.

Do not use terms used only by this project's developers.

For example, a method name `changePassword` is better than `setPassword` because it sounds more natural to end users.

## Test Description

The test description must be a plain English sentence that end users can understand.

In other words, do not use any technical terms intended only for this project's developers.
