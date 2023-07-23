## Laminar : Serverless Stream Based Processing Framework 🏔️

### Execution Guide 

`dispel4py-server`,`dispel4py-execution` and `dispel4py-client` contain induvidual instruction guides for installation and execution and should be followed in the respective order. Note that when running `redis` or `dynamic` mappings, the `redis-server` should be running in a seperate terminal. Instructions for running `redis-server` as follows:

1. Open new terminal 
2. `conda activate py37`
3. `redis-server`

Following this, any dispel4py workflow can be run within the client directory. 


### Semantic Similarity Search 

A new feature of this framework is the ability to search the Registry for PEs (Processing Elements) with natural language or code. To use this feature follow the instructions below. 

To search with natural language select the "text" option and provide the search query. Note "pe" must be specified as searches are performed on PE code. 

Text-to-code Search
```
client.search_Registry("prime","pe","text")
```

Code-to-text Search
```
client.search_Registry("random.randint(1, 1000)","pe","code")
```
