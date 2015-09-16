# gofragmentsSiteGenerator
the Go program that generates the static part of "http://gofragments.net" site.

1- written in Go,  
2- simple structure, straightforward and fast (generation in less than 1 sec for many posts),  
3- a search facility is available (simple reverse index on Title and Content),  
4- RSS/atom facility is available,  
5- multi-language support (for the time being Go only, but with a specific classification),  
6- tags, categories supported (draft doc. is not processed),  
7- rendering based on layouts/templates,    
8- Source Code syntax highlighted thanks to the tool by Andre Simon, see here: http://www.andre-simon.de/     
9- Markdown input based (using the Go "blackfriday" package by Russ Ross),       
10- Easy to evolve to a more sophisticated web/docs generator,         
11- A massive thanks to Alexander Demin, who is the original designer of this generator!   

The other part of the gofragments.net site, is an appengine/datastore(goon) standard application.

The generation of the site is in fact organized in 3 steps:  

1- pre-processing of the source code: main objective is to normalize the comments. Use of regexp and go/ast, go/parser, go/token, go/format, go/printer.  
2- generation of the markdown documents, with tags and properties, that will become the blog pages.   
3- generation of the site: which process the markdown documents and set up the static page, within the Appengine structure.  


Todos:  

1- reorganize the single program (SiteGenerator) in specialized files, in a single package.   
2- improve the integration and quality control of the 3 processes.   
3- extend the tests coverage.   
4- improve the source code annotations. Extend the number of examples, of fragments.   
5- improve the documentation (godoc).
