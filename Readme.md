# Medical API Backend Data
## Descripe
>The project is a mobile phone for configuring data for the medical API, containing records of symptoms, diseases, risk factors and period relationships, which can be used in the neo4j database, and also for obtaining information from the [health direct](https://www.healthdirect.gov.au/health-topics/conditions) website, stored in a json like format.

## Data souce
- In neo4j folder
  - Data of disease, symptom and their relations from [nature article](https://www.nature.com/articles/ncomms5212#MOESM1042)
  - Data of risk factor and relations between risk factors and disease from [wikipedia](https://www.wikipedia.org/)
- In health direct folder
  - Data from [health direct](https://www.healthdirect.gov.au/health-topics/conditions)

## Implement data
> 1. install neo4j database
> 2. open the commandline of neo4j
> 3. use Load command to import csv document to database
> > - load nodes files(disease/symptoms/risk factors) firstly    
> >`LOAD CSV WITH HEADERS  FROM "file:///filepath" AS line
> > MERGE (p:node{id:line.id,attribute1:line.attribute1,attribute2:line.attribute2})`
> > - load relations files(relation/riskfactor_disease) secondly <br>
> >`LOAD CSV WITH HEADERS FROM "file:///filepath" AS line
> >match (from:node1{node1_id:line.from_id}),(to:node2{node2_id:line.to_id})
> >`

## Tips
>Since there is no unified name for symptom on health direct, it is difficult to unify the names of symptom and summarize the relationship out of diseasease. It can be used for other databases such as mongoDB that can receive json schema
 


