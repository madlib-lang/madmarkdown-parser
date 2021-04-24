# madmarkdown-parser
Parser library for markdown format for madlib

## How to use it
Add it to the dependencies of your `madlib.json` file:
```json
{
  "dependencies": {
    "MarkdownParser": "https://github.com/madlib-lang/madmarkdown-parser/archive/refs/heads/master.zip"
  }
}
```
Run `madlib install`

```madlib
import IO from "IO"
import { parseMarkdown } from "MarkdownParser"

yourMarkdown = `
# Hello World
`

where(parseMarkdown(yourMarkdown))
  is Right ast: IO.inspect(ast)
  is Left err : IO.log(err)

```

## Run the example
```madlib
madlib install
madlib run src/Example.mad
```

## Markdown syntax currently supported

### Headings
Only the hash syntax is currently supported and stops after a line return:
```markdown
# Heading (h1)
## Heading (h2)
### Heading (h3)
#### Heading (h4)
##### Heading (h5)
###### Heading (h6)
```

### Paragraphs
Paragraphs are any text that is not part of another block type and is ended by a double line return:
```markdown
This is a paragraph
And here was added a line return

This is now a new paragraph
```

### Blockquotes
Blockquotes start with a right chevron sign (`>`) and end after a double line return:
```markdown
> This is a blockquote
```
