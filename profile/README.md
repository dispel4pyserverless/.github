## Laminar : Serverless Stream Based Processing Framework 🏔️

### Step-by-Step Installation Guide 



### Execution Notes

`dispel4py-server`,`dispel4py-execution` and `dispel4py-client` contain individual instruction guides for installation and execution and should be followed in the respective order. The client and execution application require a conda environment to run in which can be created as follows (for more details visit the respective repositories to install the required modules):

```
note conda must be installed beforehand, go to https://conda.io/projects/conda/en/stable/user-guide/install/linux.html
conda create --name py10 python=3.10
conda activate py10
```

Note that when running `redis` or `dynamic` mappings, the `redis-server` should be running in a separate terminal. Instructions for running `redis-server` as follows:

1. Open new terminal 
2. `conda activate py10`
3. `redis-server`

Following this, any dispel4py workflow can be run within the client directory. 


### Semantic Similarity Search 

A new feature of this framework is the ability to search the Registry for PEs (Processing Elements) with natural language or code. To use this feature follow the instructions below. 

To search with natural language select the "text" option and provide the search query, otherwise select the "code" option and provide a code query. Note "pe" must be specified as searches are performed on PE code. 

Text-to-code Search
```
client.search_Registry("prime","pe","text")
```

Code-to-text Search
```
client.search_Registry("random.randint(1, 1000)","pe","code")
```
