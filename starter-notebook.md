<!-- 
targets:
    - type: docker
      name: starter-notebook
      image: node:12-buster
-->

> ## [Click here 📒](https://docable.cloud/ottomatica/docable-starter-template/starter-notebook.md) to see this published notebook on `docable.cloud`.
<br>

# Starter Notebook

In this starter notebook, we explain the basic structure of a notebook file as well as some examples of supported interactive content.

Docable notebooks are markdown files which are rendered as an interactive document supporting infrastructure needed for exeuting it. The notebook files consist of two parts:

- ⚙ [Setup (optional)](#-setup-optional)
- 📄 [Notebook content](#-notebook-content)

## ⚙ Setup (optional)

> ❕ _The setup is optional and is only recommended if you need to use our more advanced computing environment management features. Otherwise our defaults will usually be sufficient._

Setup is written as a _commented_ YAML snippet in the beginning your notebook file. In setup you can specify settings related to target environments in this notebook. For example, you can configure setup to create multiple target environments which will be accessible in the notebook, or use a specific Docker image.

Here is an example for a notebook with one target environment, using `node:12-buster` Docker image. Note, if you don't include a setup snippet at all, this is the default Docable uses:

```
<!-- 
targets:
    - type: docker
      name: starter-notebook
      image: node:12-buster
-->
```

## 📄 Notebook content

The content is written in markdown (Docable also supports custom HTML snippets too, for example you can embedding your external window etc.). And to create the interactive parts of notebook, the Docable cells, we use custom markdown annotations as explained below.

> ❕ _Our custom annotations are ignored by GitHub rendering, so you can even make your `README.md` file be an interactive notebook when viewed on `docable.cloud` while still looking the same as before when viewed on GitHub._

Here is an example of this custom markdown annotation:

    ```bash | {type: 'command'}
    echo "hello world"
    ```

This ☝ is similar to a normal markdown code block with language set to `bash`. And Docable's annotation is the JSON after code block's language: `| {type: 'command'}`. This tells Docable to make code block an interactive cell behaving as a `command`. Here is how it looks when viwed as a notebook ([click here to view this on docable.cloud](https://docable.cloud/ottomatica/docable-starter-template/starter-notebook.md)):

```bash | {type: 'command'}
echo "hello world"
```

You just created your first interactive notebook cell! 🎉

...