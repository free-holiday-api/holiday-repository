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

## Repository Format
The repository is located in the `repository` folder. Inside the folder we have folders containing country code url ([ISO_3166-1_alpha-2 formatted](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)) to store each corresponding country holiday data. Each country folder would have folder defined below: 

- recurring_events    
  As the name suggests, this folder meant to store all the recurring holiday sorted by the most recent applicable time.  
- Year (YYYY)  
  -  Month (MM)  
  Year and month folder are created for non recurring events. Month folder should be inside year folder. For example holiday that meant for special occasion. 
    

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
  `1990-2000,2005-XXXX`: from year 90\` to year 00\` then from year 05\` to indefinite year  

- event:  
  Format: free string  
  The event name
