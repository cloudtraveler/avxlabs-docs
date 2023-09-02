# avxlabs-docs

Repository for lab guides for avxlabs-hosted classes including ACE, Flightschool, and Build workshops. These guides are written in [markdown](https://www.markdownguide.org/) and formatted in [jupyter{book}](https://jupyterbook.org/en/stable/intro.html)

## Prerequisites

- Python >= 3.10
- pip3 install -r requirements.txt

## Folder structure

- **_logos** - shared images across all lab guides.
- **docs** - published guide contents in subfolders (subfolder is the navigation uri for each guide).
- The rest of the folders contain the raw markdown content for each guide

## Url

Guides are hosted at: https://docs.aviatrixlab.com/[guide_name]

## Building a new lab guide

1. Clone this repository:

```bash
git clone https://github.com/AviatrixSystems/avxlabs-docs.git
```

2. Create a new branch for your work.

```bash
git checkout -b new_branch_name
```

3. Create a new folder for the new guide using the naming convention `[ace || flightschool || build]_[version]`. Example: `ace_associate`
4. Create a folder call `docs` inside your new folder. This will be the location for your markdown files. Create as many or few files as needed. Each file will be a new section in the table of contents (toc).
5. Copy the `_config.yml` and `_toc.yml` files from an existing lab guide folder and edit the files appropriately. The `toc.yml` file has references to your markdown files (without the `.md` extension) located in the `[your_folder]/docs` directory.
6. When satisfied with the content created in steps `4` adn `5`, run the following command to build your content in the `jupyter` format. At the end of the command, there will be a link to view your content in a browser.

```bash
jb build [your_folder]/
...
...
...
===================================================

Finished generating HTML for book.
Your book's HTML pages are here:
    your_folder/_build/html/
You can look at your book by opening this file in a browser:
    your_folder/_build/html/index.html
Or paste this line directly into your browser bar:
    file:///Users/your_user/Aviatrix/avxlabs-docs/your_folder/_build/html/index.html

===================================================
```

7. If satisfied with the content, copy the contents of `your_folder/_build/html/` to the root `docs` folder (not the one inside your folder) in a new folder called `your-folder`. Example: if your working directory is `./ace_associate`, your publish directory would be `./docs/ace-associate`.

8. Create a [PR](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) to have the new guide published.

## Cleanup

You can iterate and rebuild your content with the following command:

```bash
jb clean --all [your_folder]/
```
