# PFM-BE
This repository is for a web application, Pet Funeral Map. 

## Stacks
- Language
   - `Python`
- Framework
   - `FastAPI`
- IDE
   - Visual Studio Code
- Version Control
   - Github

## Infrastructure
- AWS
   - EC2
   - DynamoDB
 
## Goals
1. Fullstack development of a service
2. CI/CD if feasible

## MVP
A backend server with APIs related to sorting businesses conduct pet funeral

## Derivatives
- Reviews and ratings for funeral businesses.
- Not only funeral businesses, but also the other kinds of businesses like pet hotels, pet restaurants, and etc.

## APIs
### Business
- `GET/business?limit={LIMIT}&offset={OFFSET}`
    - **Objective**: Retrieve a list of businesses in the database, paginated.
    - **Input**: 
        - `limit: int`: number of businesses to retrieve.
        - `offset: int`: starting index of the list.
    - **Output**:
        - `JSONReponse(status_code=200, details=List[BussinessDto])`: a `JSONResponse` with status code, `200`, with detail, list of `LIMIT` number of businesses from index, `OFFSET`.

- `GET/business?name={name}&...`
    - **Objective**: Retrieve a business with the `name`
    - **Input**: 
        - `name: str`: name of the business to search.
        - `...`(Other attributes of the `BusinessDto`)
    - **Output**:
        - `JSONReponse(status_code=200, details=BussinessDto)`: A `JSONResponse` with status code, `200`, with detail, the details of the business searched(`BusinessDto`).

- `POST/business`
    - **Objective**: Adds an business to the database.
    - **Input**: _Authentication Required_
        - `body: BusinessDto`: A dictionary(`Dict[str, str]`) containing the details of a business
    - **Output**:
        - `JSONResponse(status_code=201, details={message: str}`: a `JSONResponse` with status code, `201`, with detail, `{message: 'new business is added!'}`.

- `PATCH/business?name={name}`
    - **Objective**: Updates the detail/details of a business in the database. The query parameter, `name`, is __lowered__ and __spaces omitted__, when passed.
    - **Input**: _Authentication Required_
        - `name: str`: name of the business to update.
        - `body: BusinessDto`: Details of business to be updated.
    - **Output**:
        - `JSONResponse(status_code=202, details={message: str})`: a `JSONResponse` with status code, `202`, with detail, `{message: f'{name} is updated.'}`
