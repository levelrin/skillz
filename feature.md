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

## No Gold Plating

Do not implement features that were not asked for.

Keep the feature minimal.
