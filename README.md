# Rendering DSL diagram example 

I this example you'll see how to automate rendering of [DSL](https://github.com/structurizr/dsl/blob/master/docs/language-reference.md) diagram in github markdown. 
Here is an example of [containers diagram](https://github.com/DenisPalnitsky/c4-rendering-sample/blob/main/docs/md/Containers.md)

## How it works 
- Diagram in DSL format is stored in [DSL file](diagram.dsl).

- Github Action Wokrflow uses [C4 Render action](https://github.com/marketplace/actions/c4-dsl-render-to-github-markdown) to render diagram to markdown files. Here is the [workflow file](.github/workflows/render-c4.yml) 

It also generates [Readme file](README.md) with table of content.


# C4 Intro 

DSL Language reference: https://github.com/structurizr/dsl/blob/master/docs/language-reference.md

More on C4: https://c4model.com/

Check out C4 demo: https://structurizr.com/dsl


