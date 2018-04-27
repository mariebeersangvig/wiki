# Unmodified Dataset as Output

When writing data out of Sesam you can transfer a dataset as is (unmodified dataset as output), transform the dataset on the way out or transfer directly for other sources. By transferring a dataset as it is stored you avoid sending duplicate records because the de-duplication is ensured by the dataset. E.g. you will send duplicates if the upstream dataset has a changed entity where the change is on one of the properties that you strip away.

## Benefits
- Avoid sending duplicates
- You have a log of what you sent

## Drawbacks
- Increased storage use
