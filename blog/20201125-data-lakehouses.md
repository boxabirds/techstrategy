# Data lakehouses -- Databricks training notes (25 Nov 2020)

Notes from various training resources on data lakehouses. 

Headline: Data lakehouses is a way to describe the evolution of data lakes, data warehouses and data marts to support a cloud-first model. The architecture that Databricks advocates is to use Apache Spark with Delta Lake, Databricks' open source data lakehouse tech. 

The essence, as I understand it, is fairly simple:

1. **Keep everything**. Collect all data because you don't know if you might need it in future. Leaving it in its native format is ok.
2. **Progressive structure**. Create tiers of increasing structure and cleanliness. In the Databricks data architecture overview they talk about bronze, silver and gold tiers.
3. **Work in deltas**. Make it easy to propagate updates in real time across the tiers (streaming for updates)
4. **Combine Batch & Streaming**. Make it easy to bring batch and inbound streaming together. Streams update dynamically and data flows naturally throughout the pipeline.
5. **Aspire to eliminate all data marts** The endgame is that the "gold" tier of a data lakehouse is all you need for departmental-level analytics. But there's an acceptance that data marts, that traditionally play this role of use-case specific databases, are going to be around for some time.
6. **More agile**. The multiple tiers is more complex but provides more agility. If you decide you want more data, you have it all still so you can update the transformation from one tier to the next, run a delta, and in theory the update can be done in real time. (footnote: most situations don't require real time. x minutes or x hours is often more than enough)


The benefits of cloud warehouses that stood out for me are:

1. Unlimited capacity
2. Uniform access performance (no moving of stuff around to speed up access)
3. More agility

# Resources

Databricks "How to Build a Cloud Data Lakehouse"


<iframe width="560" height="315" src="https://www.youtube.com/embed/uhVpLwjEOKU?start=110" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

[Source](https://www.youtube.com/embed/uhVpLwjEOKU?start=110)