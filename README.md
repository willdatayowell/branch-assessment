# Branch Assessment
Project created and best viewed in [Jupyter Notebooks](https://www.anaconda.com/products/individual)


## Deliverables
- Deliverable 1 - [Entity Relationship Diagram](https://dbdiagram.io/d/61fd6ea885022f4ee53ec996) or the PDF inside this project (branch-assessment-erd.pdf)
- Deliverable 2 - You're looking at it
- Deliverable 3 -
> Q: Now imagine this is a production ETL process. How would you design it? What tests would you put in place?
> 
> A:
>
> I would use business requirements to drive data quality tests and data transformation requirements before a record would get written to the source database.
>
>I would orchestrate the ETL workflow to be idempotent to ensure all CRUD functions were able to be performed successfully before anything gets written/committed to the destination warehouse. This prevents problems with failures happening in the middle of the process. If anything failed, alerts would be in place to let the responsible parties aware of the failure so swift intervention could take place. Since the process is idempotent, once the issue is fixed, the workflow can be rerun without fear of corrupting data. Included in this project is a screenshot of an idempotent workflow using an ETL tool I've used in the past (etl-screenshot.png). The example is for SCD Type 2 but the concept is the same. 

## My assumptions for this project
- There might be a data governance need to break up the data into separate tables. With no imposed restrictions however, I would prefer to store the JSON response as a whole and implementing a schema-on-read solution instead of a legacy RDBMS solution
- Dimensions were ok to be SCD Type 1 (overwritten when updated, no history)
- Storing the password and identity/ssn info in plain text was bait, so I only stored the hashed versions of those attributes
- The pros/cons of a flat schema outweighed the pros/cons of a star schema.

> #### Flat Schema (distributed UUIDs for every table)
> Pros : Simplicity of CRUD functions. Performance increase for reporting queries. Flexibility of walking the tables from any starting point.
> Cons : UUID duplication / denormalization. Slight performance hit on CRUD funtions.
>
> #### Star Schema
> Pros : Performance increase of CRUD functions. Data normalization.
> Cons : More complex ETL configuration (order of operations). Extraneous fact table for taxonomy only. Slight performance hit for reporting queries. Fact table needs to be your anchor for all queries.

[Learn more about me](shorturl.at/ruRV8)

:)
