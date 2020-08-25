---
title: Uploading to S3 via R
authors: ["harry"]
date: '2020-08-25'
slug: uploading-to-s3-via-r
categories: []
tags: []
---

Here's how to upload files from S3 using R: 

```{r}
#Create DataFrame
X <- rnorm(400, mean=70, sd=10)
Y <- rnorm(400, mean=3, sd=1)
df <- data.frame(X,Y)

#Preview
head(df)

#Save Locally
write.csv(df, "NormalRandomizedData.csv")
#Upload to S3
put_object(file = "NormalRandomizedData.csv", object = "NormalRandomizedData.csv", bucket = "iiaweb-hive-practice-data-mtcars")

#List Bucket Objects for Verification
get_bucket(bucket = bucket)
```
