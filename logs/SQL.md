### A few things learned in SQL 
- I finally got to write stored procedures. It's quite intuitive, so far. 
- Learned about `'''+@varName+'''` when referencing a variable to make them into String literal
- `CONVERT(VARCHAR()25, @timeVariable, 120)` - this is the first time that I encountered this.
It's about converting the time from `DATETIME` to `String` or `VARCHAR`. `120` is apparently the desired format of the output 
- According to chatGPT here are the formats available:
    - `101`: mm/dd/yyyy
    - `103`: dd/mm/yyyy 
    - `112`: yyyymmdd (ISO format)
    - `106`: dd Mon yyyy (e.g., 25 Dec 2024)
    - `107`: Mon dd, yyyy (e.g., Dec 25, 2024)
    - `120`: yyyy-mm-dd hh:mi:ss(24h)
    - `126`: ISO8601 format (without timezone) - yyyy-mm-ddThh:mi:ss.mmm
    - `130`: dd mon yyyy hh:mi:ss:mmmAM (or PM) (e.g., 25 Dec 2024 12:00:00:000AM)
    - `131`: dd/mm/yyyy hh:mi:ss:mmmAM (or PM) (e.g., 25/12/2024 12:00:00:000AM)
