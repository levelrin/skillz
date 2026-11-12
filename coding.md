## Package by Domain

Organize files by domain only.

Do not organize files by layers, such as UI, network, etc.

While you must structure the project by business domain, you may switch to an infrastructure-level domain, such as HTTP, file system, etc.

Distinguish each domain strictly.

In other words, do not nest domain directories.

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

For validation methods, use an adjective.

For example, you should use `user.authenticated` rather than `user.isAuthenticated`.

## No Global Scope

Do not create globally scoped variables, methods, or objects.

The only exception is the entry-point function that starts the application.

If you need to pass dependencies, just pass them through parameters.

Do not use a dependency injection container or other patterns for dependency management, even if you end up with prop-drilling (passing many parameters).

Do not create helper/utility functions at the module level either.

## No Nullable

Do not return a nullable type.

An outcome of a method or function must be a solid object.

Use validation methods instead of returning a nullable type.

Do not return a container type, such as `Optional` in Java, either.

The point is that you must provide domain context via validation methods.

Null is solely a programming concept that provides no context, which is why you must avoid it.

That does not mean you should pollute the codebase by using validation methods everywhere.

Use the validation method at the very beginning to make sure the returned value is solid.

The rest of the logic should trust the value.

Handling nulls is okay when you inevitably encounter nullable types from the SDK.

## Test Description

The test description must be a plain English sentence that end users can understand.

In other words, do not use any technical terms intended only for this project's developers.

## Fake Object

When you write a unit test, your logic may rely on external communication, such as network calls or file access.

You must use fake objects in those situations.

For example, let's say you want to test whether the user's name is displayed correctly.

First, you need to fetch the user's name from the server through a REST API.

Then, you can display the user's name.

To do that, the user object needs to make an HTTP request.

In that case, you can create a fake server object and use it as the user's dependency.

Obviously, the fake server must not send an actual HTTP request.

Instead, it returns a hard-coded fake value to the user object.

By the way, you don’t need to create fake objects if they don't communicate with external entities.
