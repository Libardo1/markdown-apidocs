# API doc generator in markdown
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://github.com/raghakot/mkdocs-apidocs/blob/master/LICENSE)

I didnt want to use sphinx and reStructuredText syntax when the rest of the documentation is in markdown. I also
dont like reStructuredText syntax. Long story short, I ended up creating my own library to auto-generate 
markdown docs per module using python `inspect` module. 

Currently only [Google formatted docstrings](http://sphinx-doc.org/latest/ext/example_google.html) are supported.
Feel free to submit a PR for extending to other formats.

## Usage
```python
from md_autogen import MarkdownAPIGenerator, to_md_file

source_folder = 'src'
github_link = 'https://github.com/raghakot/mkdocs-apidocs/blob/master'
mk_gen = MarkdownAPIGenerator(source_folder, github_link)

import mymodule
md_text = mk_gen.module2md(mymodule)
to_md_file(md_text, mymodule.__name__, "docs")
```

For usage on a real project, with [MkDocs](http://mkdocs.org), see: https://github.com/raghakot/keras-vis/tree/master/docs

The autogenerated doc on that project: https://raghakot.github.io/keras-vis/
