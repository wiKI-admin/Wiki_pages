# **Import Documents from GitHub to WikiJS**

# 

# **How\_To Guide**

| **Creation date:** | XX.XX.XXXX        |
| ------------------ | ----------------- |
| **Version 1.0:**   | XX.XX.XXXX        |
| **Author:**        | Chiragkumar Patel |

# Steps to Import Documents from GitHub to WikiJS

Instead of entering each and every document one by one to wiki, we can
upload documents in batch using GitHub. WikiJS has this feature in-built
which allows us to upload pages in batches.

**<span class="underline">Step 1: Convert .docx files into .md (Word
Document to Markdown)</span>**

We first need to convert the .docx (Word Document) to a markdown
document with .MD extension. This can be easily done by a command on
Ubuntu. To convert a single .docx document to .MD, use the command,

pandoc -f docx -t gfm example.docx -o example.md

This command will convert the word document into a GitHub-Flavored
Markdown document. “pandoc” command can be used to convert different
types of markdown documents. The user can modify the command as shown
below as per the application.

\[Link:<https://stackoverflow.com/questions/16383237/how-can-doc-docx-files-be-converted-to-markdown-or-structured-text>\]

  - \-t gfm (GitHub-Flavored Markdown)

  - \-t markdown\_mmd (MultiMarkdown)

  - \-t markdown (pandoc’s extended Markdown)

  - \-t markdown\_strict (original unextended Markdown)

  - \-t markdown\_phpextra (PHP Markdown Extra)

  - \-t commonmark (CommonMark Markdown)

In order to convert documents in Batch, user can use below mentioned
command.

\[Link: <https://ubuntuforums.org/showthread.php?t=2440432>\]

for i in \*docx; do pandoc -f markdown -t gfm -o "${i%.docx}.md"
"$i";done

**<span class="underline">Step 2: Configure Wiki.JS</span>**

  - In the Administration Area, click on Storage in the left navigation
    menu.

  - Make sure the Git storage target is checked.

  - Click on the Git tab.

  - Enter the following settings

<!-- end list -->

  - Authentication type: Basic

  - Repository URI: On your GitHub repository page, in the Code tab,
    click on the Clone or download green button and copy the URI shown
    below Clone with HTTPS. In our case it would be
    <https://github.com/wiKI-admin/Wiki_pages.git>

  - Branch: main

  - Keep all SSH settings empty or default. We don’t need to change
    that.

  - Username: wiKI-admin (This is the username of our GitHub Repository)

  - Password: Enter the password of GitHub Repository

  - Default Author Email: Email id from which GitHub Repository is
    created

  - Local Repository Path: Choose where the repo will be cloned locally
    or leave the default ./data/repo value.

<!-- end list -->

  - Set the Sync Direction to Pull from Target

  - Set the Sync Schedule to 5 minutes.

  - Click the Apply Changes button at the top of the page.

  - Wait for the Status panel to update. A new entry for Git should
    appear in green. If the bar is red, it means you have an error in
    your configuration. Go back to the Git tab, fix the error and try
    again.

**<span class="underline">Step 3: upload the converted .md markdown
files</span>**

> The Last step would be to upload the .md files on GitHub. Once you
> upload the file, the file will be imported to wikijs automatically as
> it syncs between GitHub Repository and WikiJS. The uploaded files will
> be visible as a separate page on the WikiJS server.
> 
> **<span class="underline">Step 4: Automatically structure the uploaded
> files</span>** – still looking for the solution. As of now we can
> change the path manually in wiki.
> 
> **<span class="underline">Extra step: Upload pages with
> images</span>**
> 
> In order to upload pages with images firstly we have to upload the
> image in our Github repository then, we copy that link and paste it
> between the parenthesis:
> 
> Here is the line of code so you may copy and paste it directly
> 
> \#\# \!\[\](paste-your-code-here)
