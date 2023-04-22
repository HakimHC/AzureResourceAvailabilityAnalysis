Azure Resource Availability Analysis Project
Quick Look

This project is all about analyzing and calculating the availability of Azure resources based on dummy data, focusing on the ones that have been in an 'Unavailable' state. We're leaving out resources with 'Degraded' or 'Customer Initiated' statuses, as we only want to monitor Azure's failures to ensure the promised SLA is being met.
Data Source

The main data for this project comes from a table containing dummy data. This table has all the necessary details about resource availability, timestamps, and other relevant information.
Data Preparation

Here's how we prepare the data for analysis:

    Create a temp table that filters out records with certain statuses, including 'Customer Initiated', as we only want to focus on Azure's failures.
    Set up a variable to store the number of rows for later use.
    Make another temp table that includes only resources with 'Unavailable' states.
    Build a final temp table that calculates the duration between 'Unavailable' and 'Available' states for each resource.

Data Analysis

Now, we'll calculate the availability percentage for each resource every month. Using a common table expression (CTE), we'll find the total seconds of downtime and the total percentage of uptime.

In the end, we'll have a table showing the resource ID, month, total seconds of downtime, and total percentage of uptime, sorted by resource ID and month.
Tidying Up

After the query is completed, we'll drop the temp tables to keep everything neat and tidy.
How to Use This

You can use this query to monitor Azure resource availability based on dummy data and ensure the promised SLA is being met. This information can be valuable for optimizing resources and understanding resource usage trends over time. The row variable helps us select the appropriate amount of data in the correct order.
