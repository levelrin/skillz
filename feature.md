## File Structure

The specifications must be stored in the `features` folder.

The specification must be written in a Markdown (.md) file.

Each specification file must be about a specific use case rather than a feature in general. <br>
For example, let's say we have authentication features. <br>
We support two authentication methods: password and TOTP. <br>
It's incorrect to have `features/authentication.md` and put specifications for password and TOTP in it. <br>
Instead, we must have `features/authentication/password.md` and `features/authentication/totp.md`.

There might be a case where we need to restructure files. <br>
For example, let's say we have one specification like this: `features/password-authentication.md`. <br>
Later, we decide to add one more authentication type: TOTP. <br>
In that case, we must restructure the files as follows: `features/authentication/password.md` and `features/authentication/totp.md`.

## Mandatory Sections

The specification must have the following sections, at least:
- Use Case
- Algorithm

## Use Case

The use case section must be written like this:
```markdown
## Use Case

[Insert Mermaid Flowchart]
```

## Sequence Diagram

If the feature requires the application to access external entities, we must include the sequence diagram like this:
```markdown
## Sequence Diagram

[Insert Mermaid]

### Step 4 - Authentication API

[Insert Details]
```

The `Step 4 - Authentication API` section may look random, but you will understand it better after reading the [Mermaid Sequence Diagram](mermaid-sequence.md) document.

## Prerequisites

To complete the user story, we may need to prepare something.

For example, the logic may need to access the environment variable `API_KEY`.

Such information must be written in the `Prerequisites` section like this:
```markdown
## Prerequisites

- The environment variable `API_KEY` must be set.
```

## Algorithm

Explain how the feature is technically implemented under the hood.

However, do not explain the algorithm in terms of low-level programming terms, such as raw class, method, or variable names.

Instead, use the technical domain terms to explain it conceptually.

The algorithm section must look like this:
```markdown

## Algorithm

[Insert Mermaid Flowchart]
```

## No Gold Plating

Do not implement features that were not asked for.

Keep the feature minimal.

## Explicit File Path

If a directory or file path is involved, make it explicit.

Bad Example:
> Log the error message.

Good Example:
> Log the error message in `logs/[current_datetime].log`.

## Explicit JSON Path

If JSON is involved, make the JSON path explicit.

Bad Example:
> Display the username from `user.json` with `$.name`.
