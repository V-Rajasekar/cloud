

# Amazon cloud

## Amazon Virtual Private Cloud

- VPC allows to run an isolated Network connected it to the internet or the private networks such as a corporated Network.
- when you create an EC2 instance by default it gets an VPC with a private IP address based on the rules for your VPC when we created it.

```mermaid
graph LR
	graph LR
	id1[Web server] --> id2[Data server]
```
```mermaid
%% Code  for  flowchart  below 
 graph  TB  
 sq[Square shape]  --> ci((Circle  shape)) subgraph  A  subgraph  od>Odd  shape]--  Two  line<br>edge  comment  --> ro  di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape) di==>ro2(Rounded square shape) end %% Notice that no text in shape are added here instead that is appended further down e --> od3>Really long text with linebreak<br>in an Odd shape] %% Comments after double percent signs e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز) cyr[Cyrillic]-->cyr2((Circle shape Начало)); classDef green fill:#9f6,stroke:#333,stroke-width:2px; classDef orange fill:#f96,stroke:#333,stroke-width:4px; class sq,e green class di orange
 ```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQxMDM4NTM0NCw4NTAxMjU1MjRdfQ==
-->