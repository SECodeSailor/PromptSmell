# PromptSmell

## abstract
Code smells are code structures that violate design principles and are detrimental to the quality of software. Existing approaches leverage deep learning techniques to detect code smells by extracting features from the source code. However, this approach fails to obtain enough features due to the lack of consistent rules for different code smells. Furthermore, some critical features, such as semantic correlation, code structures, and comments, may be ignored when searching the source code. Hence, we propose \textit{PromptSmell}, a novel approach to detect multi-label code smell based on prompt learning and large language models by directly employing the source code of code smell instances. Firstly, the \textit{PromptSmell} method identifies code smells in 19 real-world projects by traversing their abstract syntax trees. Secondly, it generates natural language prompts and mask tokens by integrating code snippets with prompt learning. Thirdly, this approach transforms the multi-label problem of detecting code smells into a multi-classification task by creating a customized answer space within pre-trained language models. Fourthly, the model predicts intermediate answers by filling in mask positions, and finally, these answers are mapped to target classes for final classification. This innovative technique effectively combines prompt learning and language models to enhance the identification and classification of code smells, ultimately improving software quality. We evaluate the effectiveness of \textit{PromptSmell} by comparing the results with the state of art approaches. The experimental results demonstrate that PromptSmell obtains an improvement of 21.45% in $recall_{w}$ and 18.86% in $F1_{w}$ compared to the existing approaches.

## Data collection
In each iteration of the method-level dataset, the MultiSmell is trained with 27 out of 28 projects and tested on the remaining project samples. The Minitwit project is not included in the testing process as it only contains one kind of code smell and the sample size is too tiny. The process is repeated 27 times
| Index | Project | Description |
|:------|:------|:------|
| - | Minitwit | Based on Flask's MiniTwit example |
| 1 | ArgoUML-SPL | A project that aims to extract an SPL from the current ArgoUML codebase |
| 2 | Cayenne | An open-source persistence framework, providing object-relational mapping (ORM) and remoting services |
| 3 | Cobertura | A free Java code coverage reporting tool |
| 4 | Displaytag | An open-source suite of custom tags |
| 5 | Fitjava | Integration testing framework for enhanced software development collaboration |
| 6 | Freecs | Open-source test program |
| 7 | Freedomotic | An open-source, flexible, secure Internet of Things (IoT) application framework |
| 8 | HSQLDB | A relational database management system and a set of tools written in Java |
| 9 | iText7 | A powerful PDF toolkit |
| 10 | JAdventure | Java text adventure game |
| 11 | Javacc | The most popular parser generator for use with Java applications |
| 12 | javaStud | Java tutorial example series |
| 13 | JGroups | A clustering library, allowing members to exchange messages |
| 14 | Job | Distributed scheduled job framework |
| 15 | JSmooth | A Java Executable Wrapper that builds standard Windows executable binaries (.exe) that launch java applications |
| 16 | Junit3 | A simple framework to write repeatable tests |
| 17 | Maven | A software project management and comprehension tool |
| 18 | Mylyn | Integration for Eclipse allows you to manage your Redmine issues straight from Eclipse |
| 19 | Nutch | An extensible and scalable web crawler |
| 20 | ParallelColt | A multithreaded version of Colt a library for high performance scientific computing in Java |
| 21 | PMD | A source code analyzer |
| 22 | Rhino | An open-source implementation of JavaScript written entirely in Java |
| 23 | RxJava | A library for composing asynchronous and event-based programs by using observable sequences |
| 24 | SPECjbb2005 | Application Server Testing for Java |
| 25 | Xalan | An XSLT processor for transforming XML documents into HTML, text, or other |
| 26 | Xmlgraphics-batik | A Java-based toolkit for applications that handle images in the Scalable Vector Graphics format for various purposes |
| 27 | Xmojo | JMX specification implementation |
