# Comparing Copier to other project generators

The subject of
[code scaffolding](<https://en.wikipedia.org/wiki/Scaffold_(programming)>) has been
around for some time, and there are long established good projects.

Here's a simple comparison. If you find something wrong, please open a PR and fix these
docs! We don't want to be biased, but it's easy that we tend to be:

!!! important

    Although Copier was born as a code scaffolding tool, it is today a code lifecycle
    management tool. This makes it somehow unique. Most tools below are only scaffolders
    and the comparison is not complete due to that.

<!-- Use https://www.tablesgenerator.com/markdown_tables to maintain this table -->

| Feature                                  | Copier                                   | Cookiecutter                    | Yeoman        |
| ---------------------------------------- | ---------------------------------------- | ------------------------------- | ------------- |
| Can template file names                  | Yes                                      | Yes                             | Yes           |
| Configuration                            | Single YAML file<sup>1</sup>             | Single JSON file                | JS module     |
| Migrations                               | Yes                                      | No                              | No            |
| Programmed in                            | Python                                   | Python                          | NodeJS        |
| Requires handwriting JSON                | No                                       | Yes                             | Yes           |
| Requires installing templates separately | No                                       | No                              | Yes           |
| Requires programming                     | No                                       | No                              | Yes, JS       |
| Requires templates to have a suffix      | Yes<sup>3</sup>                          | No, not configurable            | You choose    |
| Task hooks                               | Yes                                      | Yes                             | Yes           |
| Template in a subfolder                  | Not required, but you choose             | Yes, required                   | Yes, required |
| Template package format                  | Git repo<sup>2</sup>, Git bundle, folder | Git or Mercurial repo, Zip file | NPM package   |
| Template updates                         | **Yes**<sup>4</sup>                      | No                              | No            |
| Templating engine                        | [Jinja][]                                | [Jinja][]                       | [EJS][]       |

[jinja]: https://jinja.palletsprojects.com/
[ejs]: https://ejs.co/

---

<sup>1</sup> The file itself can
[include other YAML files](configuring.md#include-other-yaml-files).

<sup>2</sup> Git repo is recommended to be able to use advanced features such as
template tagging and smart updates.

<sup>3</sup> A suffix is required. Defaults to `.tmpl`, but can be configured.

<sup>4</sup> Only for git templates, because Copier uses git tags to obtain available
versions and extract smart diffs between them.
