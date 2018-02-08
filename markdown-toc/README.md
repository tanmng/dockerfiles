# markdown-toc

Run the [markdown-toc](https://github.com/jonschlinkert/markdown-toc) utility to
generate table of content for any markdown files


## Usage

Add the line `<!-- toc -->` to the file to mark the place where the utility
should write the table of content in place

Make sure to mount the markdown directory to `/source` that we you don't have to
change the working directory of the container

### Example

```bash
docker run --rm -v $PWD:/source nmtan/markdown-toc -i file_name.md
```
