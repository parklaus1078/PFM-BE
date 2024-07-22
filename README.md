# rank-your-thumbnail-BE
This repository is for a web application, Rank Your Thumbnail. It shows the videos' thumbnails with the top 5 views per published time of a youtube channel.

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
- GCP
   - GCE(Google Compute Engine) : Server instance
   - GCF(Google Cloud Firestore) : NoSQL Database
   - GCS(Google Cloud Storage) : unstructured data storage(like S3)
 
## Goals
1. Fullstack development of a service
2. CI/CD if feasible

## MVP
A backend server with APIs related to taking in a youtube channel's name, and return 5 thumbnails of the videos with highest views per day in the past 1 months.

## Derivatives
- Same output but in the past 3, 6, 12 months, and all time.
- Providing a sample thumbnail based on the output.
