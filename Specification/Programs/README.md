
# Group Programs

A Program can contain multiple Trials. A Trial can contain multiple Studies. 



## Programs-search [/brapi/v1/programs-search] 




### **Deprecated** Post Programs-search  [POST /brapi/v1/programs-search]

DEPRECATED in v1.3 - see /search/programs

 

+ Parameters


 
+ Request (application/json)
```
{
    "abbreviation": "abbreviation0",
    "leadPerson": "leadPerson0",
    "name": "name0",
    "objective": "objective0",
    "page": 0,
    "pageSize": 0,
    "programDbId": "programDbId0"
}
```



+ Response 200 (application/json)
```
{
    "metadata": {
        "datafiles": [],
        "pagination": {
            "currentPage": 0,
            "pageSize": 2,
            "totalCount": 2,
            "totalPages": 1
        },
        "status": []
    },
    "result": {
        "data": [
            {
                "abbreviation": "P1",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 1",
                "objective": "Global Population Improvement",
                "programDbId": "1",
                "programName": "Program 1"
            },
            {
                "abbreviation": "P2",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 2",
                "objective": "XYZ",
                "programDbId": "2",
                "programName": "Program 2"
            }
        ]
    }
}
```



## Programs [/brapi/v1/programs] 




### Get Programs  [GET /brapi/v1/programs{?commonCropName}{?programName}{?abbreviation}{?page}{?pageSize}]

Call to retrieve a list of programs.

 

+ Parameters
    + commonCropName (Optional, ) ... Filter by the common crop name. Exact match.
    + programName (Optional, ) ... Filter by program name. Exact match.
    + abbreviation (Optional, ) ... Filter by program abbreviation. Exact match.
    + page (Optional, ) ... Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.
    + pageSize (Optional, ) ... The size of the pages to be returned. Default is `1000`.
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization 

<strong>Bearer {token_string} </strong>




+ Response 200 (application/json)
```
{
    "metadata": {
        "datafiles": [],
        "pagination": {
            "currentPage": 0,
            "pageSize": 2,
            "totalCount": 2,
            "totalPages": 1
        },
        "status": []
    },
    "result": {
        "data": [
            {
                "abbreviation": "P1",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 1",
                "objective": "Global Population Improvement",
                "programDbId": "1",
                "programName": "Program 1"
            },
            {
                "abbreviation": "P2",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 2",
                "objective": "XYZ",
                "programDbId": "2",
                "programName": "Program 2"
            }
        ]
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Malformed JSON Request Object\nERROR - 2018-10-08T20:15:11Z - Invalid query parameter\nERROR - 2018-10-08T20:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - User does not have permission to perform this action"
```



## Search [/brapi/v1/search] 




### Post Search Programs  [POST /brapi/v1/search/programs]

Advanced searching for the programs resource.
See Search Services for additional implementation details.

 

+ Parameters
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization 

<strong>Bearer {token_string} </strong>


 
+ Request (application/json)
```
{
    "abbreviations": [
        "abbreviations0",
        "abbreviations1"
    ],
    "commonCropNames": [
        "commonCropNames0",
        "commonCropNames1"
    ],
    "leadPersonDbIds": [
        "leadPersonDbIds0",
        "leadPersonDbIds1"
    ],
    "leadPersonNames": [
        "leadPersonNames0",
        "leadPersonNames1"
    ],
    "objectives": [
        "objectives0",
        "objectives1"
    ],
    "page": 0,
    "pageSize": 0,
    "programDbIds": [
        "programDbIds0",
        "programDbIds1"
    ],
    "programNames": [
        "programNames0",
        "programNames1"
    ]
}
```



+ Response 200 (application/json)
```
{
    "metadata": {
        "datafiles": [],
        "pagination": {
            "currentPage": 0,
            "pageSize": 0,
            "totalCount": 0,
            "totalPages": 0
        },
        "status": []
    },
    "result": {
        "searchResultDbId": "551ae08c-4548-4bde-ad70-f23beb25e2ea"
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Malformed JSON Request Object\nERROR - 2018-10-08T20:15:11Z - Invalid query parameter\nERROR - 2018-10-08T20:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - User does not have permission to perform this action"
```





### Get Search Programs by searchResultsDbId  [GET /brapi/v1/search/programs/{searchResultsDbId}{?page}{?pageSize}]

Advanced searching for the programs resource.
See Search Services for additional implementation details.

 

+ Parameters
    + searchResultsDbId (Required, ) ... Permanent unique identifier which references the search results
    + page (Optional, ) ... Which result page is requested. The page indexing starts at 0 (the first page is 'page'= 0). Default is `0`.
    + pageSize (Optional, ) ... The size of the pages to be returned. Default is `1000`.
    + Authorization (Optional, ) ... HTTP HEADER - Token used for Authorization 

<strong>Bearer {token_string} </strong>




+ Response 200 (application/json)
```
{
    "metadata": {
        "datafiles": [],
        "pagination": {
            "currentPage": 0,
            "pageSize": 2,
            "totalCount": 2,
            "totalPages": 1
        },
        "status": []
    },
    "result": {
        "data": [
            {
                "abbreviation": "P1",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 1",
                "objective": "Global Population Improvement",
                "programDbId": "1",
                "programName": "Program 1"
            },
            {
                "abbreviation": "P2",
                "commonCropName": "Tomatillo",
                "documentationURL": "https://brapi.org",
                "leadPerson": "Name Nameson",
                "leadPersonDbId": "person1",
                "leadPersonName": "Name Nameson",
                "name": "Program 2",
                "objective": "XYZ",
                "programDbId": "2",
                "programName": "Program 2"
            }
        ]
    }
}
```

+ Response 400 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Malformed JSON Request Object\nERROR - 2018-10-08T20:15:11Z - Invalid query parameter\nERROR - 2018-10-08T20:15:11Z - Required parameter is missing"
```

+ Response 401 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - Missing or expired authorization token"
```

+ Response 403 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - User does not have permission to perform this action"
```

+ Response 404 (application/json)
```
"ERROR - 2018-10-08T20:15:11Z - The requested object DbId is not found"
```

