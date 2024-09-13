# PromptSmell

## abstract
Code smells are code structures that violate design principles and are detrimental to the quality of software. Existing approaches leverage deep learning techniques to detect code smells by extracting features from the source code. However, this approach fails to obtain enough features due to the lack of consistent rules for different code smells. Furthermore, some critical features, such as semantic correlation, code structures, and comments, may be ignored when searching the source code. Hence, we propose PromptSmell, a novel approach to detect multi-label code smell based on prompt learning and large language models by directly employing the source code of code smell instances. Firstly, the PromptSmell method identifies code smells in 19 real-world projects by traversing their abstract syntax trees. Secondly, it generates natural language prompts and mask tokens by integrating code snippets with prompt learning. Thirdly, this approach transforms the multi-label problem of detecting code smells into a multi-classification task by creating a customized answer space within pre-trained language models. Fourthly, the model predicts intermediate answers by filling in mask positions, and finally, these answers are mapped to target classes for final classification. This innovative technique effectively combines prompt learning and language models to enhance the identification and classification of code smells, ultimately improving software quality. We evaluate the effectiveness of PromptSmell by comparing the results with the state of art approaches. The experimental results demonstrate that PromptSmell obtains an improvement of 21.45% in $recall_{w}$ and 18.86% in $F1_{w}$ compared to the existing approaches.

## Data collection
To ensure the diversity of the dataset, 19 real-world projects are selected from multiple domains. These projects are presented in Table, where NOC represents the number of classes, NOM represents the number of methods, and LOC is the number of lines of code. A total of 15143 classes are included in the 19 projects, with 52.6% of the projects containing more than 500 classes. This dataset involves 139,446 methods. Most projects include more than 1,000 numbers of methods. The total lines of code (LOC) is 1,620,112. Most projects contain more than 10,000 LOC. 

| Index | Project | Description | NOC | NOM | LOC | 
|:------|:--------|:------------|:----|:----|:----|
| 0 | ArgoUML | A software application for drawing UML diagrams | 1,931 | 17,129 | 157,611 |
| 1 | Art of Illusion | An open-source 3D modelling and rendering software in Java | 487 | 6,672 | 102,679 |
| 2 | Cayenne | An open-source persistence framework, providing object-relational mapping (ORM) and remoting services | 2,983 | 17,415 | 137,928 |
| 3 | Cobertura | A tool for Java code coverage reporting | 165 | 1,156 | 14,723 |
| 4 | Freecs | A testing program for an open-source free chat server | 139 | 1,404 | 20,720 |
| 5 | Freemind | A software for mind mapping based on Java | 532 | 7,303 | 65,866 |
| 6 | HSQLDB | A system of relational database management | 664 | 13,060 | 225,106 |
| 7 | iText7 | An application for creating, adjusting, checking, and maintaining PDF documents | 1,624 | 12,551 | 118,717 |
| 8 | Ant-Ivy | A tool for managing (recording, tracking, resolving, and reporting) project dependencies | 439 | 3,087 | 21,781 |
| 9 | Javacc | An application that generates syntax and lexical analyzers | 180 | 1,487 | 20,886 |
| 10 | JHotDraw | A graphical editor framework that supports development in Java | 488 | 4,434 | 41,105 |
| 11 | Maven | A tool for project construction, dependency management, and project information management of Java projects | 731 | 3,929 | 21,703 |
| 12 | Mybatis | A tool to support custom SQL, stored procedures, and advanced mapping | 118 | 534 | 3,702 |
| 13 | Mylyn | A plugin for seamless task and context management integration into Eclipse | 183 | 1,064 | 10,660 |
| 14 | ParallelColt | A high-performance computing tool that includes algorithms for data analysis, Fourier transforms, etc | 1,130 | 14,527 | 216,685 |
| 15 | Rhino | An open source project for executing JavaScript programs in the Java environment | 628 | 6,414 | 75,341 |
| 16 | SPECjbb2005 | A benchmarking program for evaluating the performance of server-side Java applications | 76 | 747 | 12,716 |
| 17 | Xalan Java | A tool for converting XML documents to HTML, text, or other XML document types | 963 | 102,86 | 185,511 |
| 18 | XML Graphics Batik | A tool for working with images in scalable vector graphics format | 1,682 | 16,247 | 166,672 |
| Total |  | | 15,143 | 139,446 | 1,620,112 |

(Generalised datasets)
| Index | Project | Description | NOC | NOM | LOC | 
|:------|:--------|:------------|:----|:----|:----|
| 0 | Drjava | An open-source software for evaluating the capabilities of Java code | 1,145 | 16,919 | 147,245 |
| 1 | Filecrush | A utility program that fixes small files by merging them into larger files | 23 | 311 | 6,130 |
| 2 | Freeplane | A tool that provides mind mapping and navigation to map information | 1,112 | 9,946 | 70,019 |
| 3 | JGroups | A tool is a reliable group communication toolkit written entirely in Java | 249 | 2,005 | 13,624 |
| 4 | Nutch | An open source framework for crawling the web content | 370 | 2,008 | 23,298 |
| 5 | PMD | An Extensible Multilingual Static Code Analyser | 2,339 | 11,063 | 56,510 |

