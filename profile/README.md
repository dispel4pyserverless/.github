# Laminar : Serverless Stream Based Processing Framework 🏔️

## Step-by-Step Installation Guide 

There are three components to this framework which must be installed and executed. To run the whole framework and test with a sample program follow the instructions below:

### Framework 
First, create a new directory which will contain all the framework components.
```
/data> mkdir Laminar
/data> cd Laminar
/data/Laminar> 
```
### Server Installation and Execution 
Open a new terminal with the new `Laminar` directory. 
```
/data/Laminar> 
```
Clone the server application repository.
```
/data/Laminar> git clone https://github.com/dispel4pyserverless/dispel4py-server.git
```
Enter the server directory.
```
/data/Laminar> cd dispel4py-server
```
To manage permission issues, run:
```
/data/Laminar/dispel4py-server> chmod +x gradlew
```
To run the server
```
/data/Laminar/dispel4py-server> ./gradlew bootRun
```
The server will now be running, and ready to receive requests. You should see this sample output 
```
/data/Laminar/dispel4py-server>
...
com.dispel4py.rest.RestApplication: Started RestApplication in 66.905 seconds (JVM running for 69.911)
...
```
### Execution Installation and Execution
Open a new terminal with the `Laminar` directory. 
```
/data/Laminar> 
```
Clone the execution application repository.
```
/data/Laminar> git clone https://github.com/dispel4pyserverless/dispel4py-execution.git
```
Enter the execution directory.
```
/data/Laminar> cd dispel4py-execution 
```
In order to run the application you need to create a new Python 3.10 environment. Note conda must be installed beforehand, go to https://conda.io/projects/conda/en/stable/user-guide/install/linux.html
```
/data/Laminar/dispel4py-execution> conda create --name py10 python=3.10
/data/Laminar/dispel4py-execution> conda activate py10
```
Install dispel4py
```
(py10) /data/Laminar/dispel4py-execution> git clone https://github.com/dispel4py2-0/dispel4py.git
(py10) /data/Laminar/dispel4py-execution> cd dispel4py
(py10) /data/Laminar/dispel4py-execution/dispel4py> pip install -r requirements.txt
(py10) /data/Laminar/dispel4py-execution/dispel4py> python setup.py install
(py10) /data/Laminar/dispel4py-execution/dispel4py> cd ..
(py10) /data/Laminar/dispel4py-execution>
```
Test dispel4py.
```
(py10) /data/Laminar/dispel4py-execution> dispel4py simple dispel4py.examples.graph_testing.word_count -i 10
```
Install app modules.
```
(py10) /data/Laminar/dispel4py-execution> pip install -r requirements_app.txt
```
Run application
```
(py10) /data/Laminar/dispel4py-execution> flask run 
```
The execution engine will now be running and ready to receive requests from the server. The sample output will be as follows:
```
(py10) /data/Laminar/dispel4py-execution>
...
Running on http://127.0.0.1:5000
...
```
### Client Installation and Execution
Open a new terminal with the `Laminar` directory. 
```
/data/Laminar> 
```
Clone the client application repository.
```
/data/Laminar> git clone https://github.com/dispel4pyserverless/dispel4py-client.git
```
Enter the client directory.
```
/data/Laminar> cd dispel4py-client
```
Activate the conda environment previously created.
```
/data/Laminar/dispel4py-client> conda activate py10
```
Install dispel4py.
```
(py10) /data/Laminar/dispel4py-client> git clone https://github.com/dispel4py2-0/dispel4py.git
(py10) /data/Laminar/dispel4py-client> cd dispel4py
(py10) /data/Laminar/dispel4py-client/dispel4py> pip install -r requirements.txt
(py10) /data/Laminar/dispel4py-client/dispel4py> python setup.py install
(py10) /data/Laminar/dispel4py-client/dispel4py> cd ..
(py10) /data/Laminar/dispel4py-client>
```
Test dispel4py.
```
(py10) /data/Laminar/dispel4py-client> dispel4py simple dispel4py.examples.graph_testing.word_count -i 10
```
Install client modules
```
(py10) /data/Laminar/dispel4py-client> pip install -r requirements_client.txt
```
Copy sample client program to `dispel4py-client` directory.
```
(py10) /data/Laminar/dispel4py-client> cp CLIENT_EXAMPLES/sample.py .
```
Run sample client program.
```
(py10) /data/Laminar/dispel4py-client> python sample.py
```
## Additional Execution Notes

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
