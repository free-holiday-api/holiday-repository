# Holiday Repository
A repository that contains holiday database from around the world.
Repository would contains all the holiday listing around the world.
Please see format in thie readme section. Contribution welcome!

We also plan to use github pages to serve in JSON format, so everyone can have access to the API!

# Roadmap
- (In progress) Initialize repo format and convention.
- (Todo) CSV file checker, to enforce the convention. 
- (Todo) Library to generate JSON from csv repository. 
   
  See: https://github.com/khasburrahman/csv-date-event-static-api-generator
- (Todo) Github static API pages

## Contribution Guide
As of now the repo is only available for holiday repo contribution. 
Please provide the source of truth (prefer government website / open wiki). 
- Fork this repo
- Clone the fork
- Submit the PR! 

## Repository Format
The repository is located in the `repository` folder. Inside the folder we have folders containing country code url ([ISO_3166-1_alpha-2 formatted](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)) to store each corresponding country holiday data. Inside of country folder we have: 

- recurring events file    
  As the name suggests, this file meant to store all the recurring holiday in that year.  
- Yearly file  
  This would store yearly holiday that are not recurring / special occasion. 
    

## CSV File format
### Columns: 

- date:  
  Format: (mm-dd-yyyy)  
  For `recurring_events`, please fill the year as XXXX to differentiate with non `recurring_events`, also prefer to put it before any `recurring_events`

- category:  
  Format: country [ISO_3166-1_alpha-2 formatted](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) code  

- repeatable:  
  format: ("T"/"F")  
  Boolean value representing is the event repeatable

- repeatable_year_period:  
  format: (yyyy-yyyy) [required if repeatable, seperated by comma]  
  Year range where the events is applicable, use XXXX for indefinite year  
  Sort the range for more readable value   
  For example:  
  `XXXX-2000`: from indefinite year to year 2000  
  `1990-2000`: from year 90\` to year 00\`  
  `1990-2000`: from year 90\` to year 00\`  
  `2005-XXXX`: from year 05\` to indefinite year  

- event:  
  Format: free string  
  The event name
### File name
Format for the file name should be  
For non recurring holiday: `{country code ISO_3166-1_alpha-2}-{Year YYYY}.csv`  
For recurring holiday: `{country code ISO_3166-1_alpha-2}-recurring_events.csv`

Example: 
- `ID-2020.csv`
- `ID-recurring-events.csv`