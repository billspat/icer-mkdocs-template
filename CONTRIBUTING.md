# Docs style guide

- File names are Title Capitals with underscores replacing spaces, e.g. 
HPCC_Module_System.md
- Documents should use as much native Markdown as possible. See 
<https://www.markdownguide.org/>
- Images and file attachments are placed in docs/attachments, in folders named
like the markdown file they are used in
- All pages should go in the nav bar, which requires editing the `nav` section of mkdocs.yml
- Apply principles of Diataxis when writing documentation for an ICER project, see  https://diataxis.fr/.  
- Tag pages appropriately as you go.

For all other style questions (e.g. pronouns usage) see the MSU style guide
<https://comms.msu.edu/resources/editorial-style-guide> and the inclusive guide
<https://brand.msu.edu/storytelling/inclusive-guide>


# Lab Notebooks style guide

- Not all ICER projects will use 'Lab Notebooks' 
- Lab notebooks should be built from the file templates/LabNotebook_template.md
- File names should be LabNotebook_Topic_Name.md
- Lab notebooks should have a title included in the header following the format 
`Lab Notebook: Topic Name`.

# Tag style guide

- Pages should be tagged based on their contents and purpose.
- Purpose-based tags should follow the [Diataxis standard](https://diataxis.fr/). Note that `how-to guide` should be hyphenated.
- Proper noun tags (i.e. software-related tags) should be capitalized according to their "official" style. For example, PyTorch, MATLAB, and Conda.
- Software best recognized by its all-lowercase command line invocation should correspondingly be written in lowercase (e.g. ssh, git)
- General topics should be lowercase (e.g. interactive desktop, containers)