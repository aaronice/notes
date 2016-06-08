# Normalization or Denormalization

### Pros and Cons of a Normalized database design.

**Normalized databases fair very well under conditions where the applications are write-intensive and the write-load is more than the read-load.** This is because of the following reasons:

- Normalized tables are usually smaller and have a smaller foot-print because the data is divided vertically among many tables. This allows them to perform better as they are small enough to get fit into the buffer.
- The updates are very fast because the data to be updated is located at a single place and there are no duplicates.
- Similarly the inserts are very fast because the data has to be inserted at a single place and does not have to be duplicated.
- The selects are fast in cases where data has to be fetched from a single table, because normally normalized tables are small enough to get fit into the buffer.
- Because the data is not duplicated so there is less need for heavy duty group by or distinct queries.

Although there seems to be much in favor of normalized tables, with all the pros outlined above, but the main cause of concern with fully normalized tables is that normalized data means joins between tables. And this joining means that read operations have to suffer because **indexing strategies do not go well with table joins**.

Now lets have a look at the pros and cons of a denormalized database design.

### Pros and cons of denormalized database design.

**Denormalized databases fair well under heavy read-load and when the application is read intensive.** This is because of the following reasons:

- The data is present in the same table so there is no need for any joins, hence the selects are very fast.
- A single table with all the required data allows much more efficient index usage. If the columns are indexed properly, then results can be filtered and sorted by utilizing the same index. While in the case of a normalized table, since the data would be spread out in different tables, this would not be possible.

Although for reasons mentioned above selects can be very fast on denormalized tables, **but because the data is duplicated, the updates and inserts become complex and costly.**

Having said that neither one of the approach can be entirely neglected, because a real world application is going to have both read-loads and write-loads. Hence the correct way would be to utilize both the normalized and denormalized approaches depending on situations.

### Final words.
Although, denormalized schema can greatly improve performance under extreme read-loads but the updates and inserts become complex as the data is duplicate and hence has to be updated/inserted in more than one places.




## Reference

- [Databases: Normalization or Denormalization. Which is the better technique?](http://www.ovaistariq.net/199/databases-normalization-or-denormalization-which-is-the-better-technique/#.V1IKTRQrJE4)
