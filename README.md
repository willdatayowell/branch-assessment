# Branch Assessment
Project created and best viewed in [Jupyter Notebooks](https://www.anaconda.com/products/individual)

[Entity Relationship Diagram](https://dbdiagram.io/d/61fd6ea885022f4ee53ec996)


### My assumptions for this project
- There was data governance need to break up the data into separate tables. With no imposed restrictions, I would prefer to store the JSON response as a whole and implementing a schema-on-read solution instead of a legacy RDBMS solution like this which would change the workflow from ETL to ELT
- The UUID could be trusted to be used as a true universally unique identifier
- Dimensions were to be SCD type 1 (overwritten when updated, no history)
- Storing the password and identity/ssn info in plain text was bait, so I only stored the hashed versions of those attributes

### Other things worth mentioning
- I might have created an enum type to whitelist possible identity types if I knew all possible options
- [Learn more about me](shorturl.at/ruRV8)
- Deliverable 3 is in the form of the production-etl-notes.txt file