<!-- 
targets:
    - type: docker
      name: starter-notebook
      image: node:12-buster
-->

> ## [Click here 📒](https://docable.cloud/ottomatica/docable-starter-template/starter-notebook.md) to see this published notebook on `docable.cloud`.

# Starter Notebook

In this starter notebook, we explain the basic structure of a notebook file as well as some examples of supported interactive content.

Docable notebooks are markdown files which are rendered as an interactive document supporting infrastructure needed for exeuting it. The notebook files consist of two parts:

- ⚙ [Setup (optional)](#-setup-optional)
- 📄 [Notebook content](#-notebook-content)

## ⚙ Setup (optional)

> ❕ _The setup is optional and is only recommended if you need to use our more advanced computing environment management features. Otherwise our defaults will usually be sufficient and you can skip to the next section about notebook content._

Setup is written as a _commented_ YAML snippet in the beginning your notebook file. In setup you can specify settings related to target environments in this notebook. For example, you can configure setup to create multiple target environments which will be accessible in the notebook, or use a specific Docker image.

Here is an example for a notebook with one target environment, using `node:12-buster` Docker image. Note, if you don't include a setup snippet at all, this is the default Docable uses:

    <!-- 
    targets:
        - type: docker
        name: starter-notebook
        image: node:12-buster
    -->

## 📄 Notebook content

The content is written in markdown (Docable also supports custom HTML snippets too, for example you can embedding your external window etc.), so you can use the same markdown syntax you always used on GitHub. And to create the interactive parts of notebook, the cells, you will use Docable's custom markdown annotations as explained below.

> ❕ _Our custom annotations are ignored by GitHub rendering, so you can even make your `README.md` file be an interactive notebook when viewed on `docable.cloud` while still looking the same as before when viewed on GitHub._

Here is an example of this custom markdown annotation:

    ```bash | {type: 'command'}
    echo "hello world"
    ```

As you can see, this Docable cell ☝ is similar to a normal markdown code block with language set to `bash`. The difference with normal markdown is the JSON after code block's language: `| {type: 'command'}`. This is what tells Docable to make code block an interactive cell behaving as a `command`. Here is how it looks when viwed as a notebook ([click here to view this on docable.cloud](https://docable.cloud/ottomatica/docable-starter-template/starter-notebook.md)):

```bash | {type: 'command'}
echo "hello world"
```

You just created your first interactive notebook cell! 🎉

Now that you've seen what a basic Docable JSON annotation looks like, [here is](https://github.com/ottomatica/docable-notebooks#quick-reference) the list of supported content `type`s and their modifiers. 
### Examples

See some examples of supported content below, or _checkout more advanced examples in [`ottomatica/docable-examples` notebook](https://docable.cloud/ottomatica/docable-examples)._

#### Command cell with a variable:

    ```bash|{type:'command', variables: 'name'}
    echo "hello {{name}}"
    ```

```bash|{type:'command', variables: 'name'}
echo "hello {{name}}"
```

#### Script cell with language set to js (javascript):

    ```js |{type:'script'}
    let id = Math.random().toString(36).substring(2);
    console.log(id);
    ```

```js |{type:'script'}
let id = Math.random().toString(36).substring(2);
console.log(id);
```

### File cell to create a file with this content in `/tmp/docable_file`

    ```bash|{type:'file', path:'/tmp/docable_file', variables: 'name'}
    hello 
    {{name}}
    ```

```bash|{type:'file', path:'/tmp/docable_file', variables: 'name'}
hello 
{{name}}
```

### Terminal cell (by default using bash)

    ```|{type:'terminal'}
    ```

```|{type:'terminal'}
```

### Terminal cell showing a node REPL

    ```|{type:'terminal', command: 'node'}
    ```

```|{type:'terminal', command: 'node'}
```

#### Quiz cell with language set to js (javascript):

    Docable notebooks support embedding a terminal.
    ```js|{type:'quiz', quiz_type:'singlechoice', quiz_answers:'0'}
    - [ ] true
    - [ ] false
    ```

Docable notebooks support embedding a terminal.
```js|{type:'quiz', quiz_type:'singlechoice', quiz_answers:'0'}
- [ ] true
- [ ] false
```

#### Info cell with lines 5 to 6 highlighted

    ```bash|{type:'info', range: {start:5, end: 6}}
    $ ls -la
    total 4568
    -rw-r--r--    1 foo  staff    11340 Sep  4 19:21 LICENSE
    -rw-r--r--    1 foo  staff     7745 Sep 28 21:17 README.md
    -rwxr-xr-x    1 foo  staff     8841 Jan 28 18:23 index.js
    -rw-r--r--    1 foo  staff   199945 Jan 26 14:46 package-lock.json
    -rw-r--r--    1 foo  staff     1991 Jan 30 14:23 package.json
    ```

```bash|{type:'info', range: {start:5, end: 6}}
$ ls -la
total 4568
-rw-r--r--    1 foo  staff    11340 Sep  4 19:21 LICENSE
-rw-r--r--    1 foo  staff     7745 Sep 28 21:17 README.md
-rwxr-xr-x    1 foo  staff     8841 Jan 28 18:23 index.js
-rw-r--r--    1 foo  staff   199945 Jan 26 14:46 package-lock.json
-rw-r--r--    1 foo  staff     1991 Jan 30 14:23 package.json
```

#### Embed slides

    ```|{type:'slides'}
    https://docs.google.com/presentation/d/e/2PACX-1vSl94Tz9pRTwp1LTR6ImmHoHqd7kHiresyP-Ytq0HnPdjqdK38MtxMvr4agOykQPqDIQrixKtW27mlT/embed
    ```

```|{type:'slides'}
https://docs.google.com/presentation/d/e/2PACX-1vSl94Tz9pRTwp1LTR6ImmHoHqd7kHiresyP-Ytq0HnPdjqdK38MtxMvr4agOykQPqDIQrixKtW27mlT/embed
```

See more (advanced) examples in [`ottomatica/docable-examples` notebook](https://docable.cloud/ottomatica/docable-examples).
