# 🪷 suna - static blog generator

**Suna is:**

-  A Static Blog Processor/Generator.
-  A Markdown to HTML parser.
-  An HTML-Templating Engine.
-  Minimal.
-  Written in POSIX-Compliant Shell, making it very portable.

# 📖 Installation & Usage

#### Clone the git repository.

  ``` bash
  git clone https://github.com/fuku77/suna && cd suna
  ```
  
#### Run the script
Simply run the script:
<br>

```
./suna 
```

You should see some new files & folders inside `root`.
You can take a look at the files to make sure it generated correctly.
<br>
Now you can change the `root` directory to where you want to host your web server by using `--output DIR` or by editing `config`

# ⚙C Configuration

You can run `suna -h` to get a brief explanation of all the command-line options.
|||
| --- | --- |
| outputDir | `root` by default. |
| templateFile | `.suna/template.html` by default. Default template file used for all files, unless explicitely stated otherwise through rules. |
| logFile | `.suna/suna.log` by default. |
| action | Default action performed when no action arguments are given. Valid actions can be found inside `config`. |
| logSize | Maximum size for logFile (in lines). |
| verbose | Default verbosity. |

# 📚 Rules & Macros
Macros are set to their values during parsing.
Macros can be used either inside the template or the markdown source files.
- Macro syntax: `{{ MACRO }}`
- Rule syntax:
  ```
  <!-- {
    !rule1 "foo"
    !rule2 "bar"
  } -->
  ```

---

| Macro | Value |
| - | - |
| TITLE | The title of the document. |
| CONTENT | Parsed result of the file. This is a special macro, as it can only be used inside the HTML template. |

---

| Rule | Value |
| - | - |
| title | Used for the `TITLE` macro. Falls back to the first header in file if not given, otherwise falls back to file name |
| template | Specify a different template for the file. Note that the path must be relative to `.suna`, so `!template "foo.html"` will result in `.suna/foo.html`. |
