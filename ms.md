# Scriptoria

### Authors

* Philippe Desjardins-Proulx
* Timothée Poisot
* Dominique Gravel

## Abstract

## Motivation

The recent surge in the use of preprints [@des2013] and the development of
a whole ecosystem of open-science applications calls into question the
relevance of peer review as a limiting step in the diffusion of scientific
knowledge. In the current publication model, research outputs have limited
visibility before they are formally vetted by two or more members of the
academic community. As problematic as the delay between finalization and
diffusion of the output is, the limited opportunity for constructive dialogue
during the elaboration of a manuscript is an even bigger challenge that needs
be overcame, if we assume that the ultimate goal of peer review is the improve
the quality of published articles. We argue that both shortcomings can be
addressed at the same time, if authors turn towards a new model to write
scholarly literature.

The basic process of writing a scientific document hasn't changed much in the
last few hundred years. A document is written and submitted to a small
committee that will evaluate its content and make suggestions. The composition
of this committee is left to the discretion of the editor (and often, to the
availability of expert referees at the time the article is submitted
*cite refs. tragedy ref commons*). It is reasonable to think that the
improvement in the quality of published papers would be greater if
manuscripts were commented upon (i) early in the writing process, and (ii)
by a wider audience. In addition, the current reviewing and publishing
process is slow and done behind closed doors. There are faster, and more
open, ways to develop and evaluate documents. Modern software engineers
(authors) rely on a sophisticated, and well studied, methodology for
developing source code (literature) and rigorously review and improve them.
Software engineers have to write thousands of lines of code in coordination,
detect errors in the code (suggested modifications to the document), and fix
them. This process is essentially the same as the process of writing
academic papers in collaboration, as it strives to produce the more concise,
efficient, and informative output by the end.

* Discuss revision control & bug tracking.
* Git in science [@ram2013].
* Git/Mercurial/Bazaar are decentralized (which is good)...
* ...what we need is a tool to track the repositories.
* Scriptoria offers a single API/WUI to track repositories with manuscripts.

## Box 1: Technical details

* What are git, mercurial, bazaar?
* Where can I store repositories?
* What is a clone, a fork?

## Description

### Website

A basic description of how the website works.

* Users add repositories with a scriptoria.json file at the root.
* The website stores the info and track the repository (e.g.: last activity, DOI, etc...).
* Users can browse the repositories via the web user interface.
* Developers can build tools using scriptoria's RESTful API.

### Format

To be included in Sciptoria's database, a repository must have a file named
`scriptoria.json` (all in lowercase) at its root (Box 2). JSON is a common
human-readable format used for (well everything...).  A basic JSON file for
scriptoria will have the following entries: **source** establishes the address
of the original repository for the article. It is used to avoid confusion if
the repository is cloned or forked. **type** is one of: 'article', 'thesis',
'book', 'book chapter', 'conference'. **status** is either 'published',
'under review' or 'in preparation'.  If this entry is not set, it will
default to 'in preparation', unless a doi is provided, in which case it
will always be set to 'published'. **title** and **abstract** are also
mandatory and each are represented by a single string. **authors** is an
array of maps, i.e.: it must be enclosed by squared brackets and contains
information on each author within brackets. For each author, the **first
name**, **last name**, and **email** entries must be provided.
`Scriptoria.info` has a formal description of the JSON format along with
a validator: URL (a simple tool to write scriptoria.json files perhaps?).

## Box 2: Sample JSON file

``` json
{
"source": "https://github.com/karthikram/smb_git",
"type": "ms",
"status": "published",
"title": "Git: A powerful tool to facilitate greater reproducibility and
transparency in science",
"abstract": "Git is a powerful version control system that is widely used in
software development. The features of Git that make it popular among software
developers also makes it ideal for managing research workflows. In this article
I describe how the power of Git could be leveraged in a scientific context to
improve reproduciblity, increase transparency, and make it easy for others to
build upon existing work. I also provide a handful of real-world use cases
describing how Git and Git hosting services such as GitHub can enhance
collaborative efforts, lower barriers to data re-use, and accelerate
development of new ideas.",
"authors": [{
"first name":"Karthik",
"last name":"Ram",
"email":"karthik.ram@berkeley.edu",
"orcid":"0000-0002-0233-1757",
"first": True,
"corresponding": True
}],
"doi": "doi:10.1186/1751-0473-8-7"
}
```

* Add screenshot of the resulting entry on Scriptoria.info

## Discussion

* The discussion should focus on applications of the API, and how it could be intergrated in science [@ram2013].
* How it will impact the current scientific process

## Acknowledgements

