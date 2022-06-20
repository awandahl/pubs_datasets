# pubs_datasets

Links to different datasets of publication metadata and citations

#### [OpenAlex](https://openalex.org/) will replace [Microsoft Academic Graph](https://www.microsoft.com/en-us/research/project/academic/articles/microsoft-academic-to-expand-horizons-with-community-driven-approach/) in Dec 2021   

[Jason Priem´s presentation at NIH June 9th 2022](https://videocast.nih.gov/watch=45658)    
[Same at Youtube](https://www.youtube.com/watch?v=LBfBBQ9_KTk)    

[Code](https://github.com/ourresearch)    

[AWS S3 Explorer](http://openalex.s3.amazonaws.com/browse.html)
````
http://openalex.s3.amazonaws.com/browse.html
````
[Filters](https://docs.openalex.org/api/get-lists-of-entities/filter-entity-lists)

[KTH all years grouped by OA status](https://api.openalex.org/works?filter=institutions.id:I86987016&group_by=oa_status) 
````
https://api.openalex.org/works?filter=institutions.id:I86987016&group_by=oa_status
````
[KTH 2022-01-01 to 2022-06-20 group by OA status](https://api.openalex.org/works?filter=institutions.id:I86987016,from_publication_date:2022-01-01,to_publication_date:2022-06-20&group_by=oa_status)  
````
https://api.openalex.org/works?filter=institutions.id:I86987016,from_publication_date:2022-01-01,to_publication_date:2022-06-20&group_by=oa_status
````
[KTH 2022-01-01 to 2022-06-20 group by publisher](https://api.openalex.org/works?filter=institutions.id:I86987016,from_publication_date:2022-01-01,to_publication_date:2022-06-20&group_by=host_venue.publisher)    
````
https://api.openalex.org/works?filter=institutions.id:I86987016,from_publication_date:2022-01-01,to_publication_date:2022-06-20&group_by=host_venue.publisher
````

-------------------------

#### [Open Citations](https://opencitations.net/)    
[COCI](https://opencitations.net/index/coci): the OpenCitations Index of Crossref open DOI-to-DOI citations     
[COCI REST API](https://opencitations.net/index/coci/api/v1)

-------------------------

#### Refcat: The Internet Archive Scholar Citation Graph      
Paper in arXiv: https://arxiv.org/pdf/2110.06595.pdf     
Gitlab: https://gitlab.com/internetarchive/refcat     
Builds upon:    
https://fatcat.wiki/  
see https://guide.fatcat.wiki/

-------------------------

#### Altmetrics     
[Altmetric.com API](https://api.altmetric.com/v1/doi/10.1126/sciadv.abe4724)     

#### CORE    
https://core.ac.uk/
