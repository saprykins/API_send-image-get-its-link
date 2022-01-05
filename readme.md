# API TO SAVE FILES AND GET LINKS TO FILES FROM TAGS

# OVERVIEW
API that receives and saves png file in local database.  
API allows to retrieve link on local machine from via its tag.  
No authentication required

# INSTALLATION (UBUNTU OS)

Create vitual environment  

  As an example, you can call it venv and simply type: 
  ```
  $ sudo virtualenv venv
  ```
* If you do not have virtual environment tool installed, you can install it from command line:    
  ```
  $ sudo apt install python3-virtualenv
  ```

Activate the virtual environment you have just created (in Ubuntu): 
```
$ source ./venv/bin/activate
```
Activate the virtual environment you have just created (in Windows): 
```
$ source ./venv/Scripts/activate
```
Install the packages that application requires typing in command line:  
```
$ pip install -r requirements.txt
```

# USAGE

## Run the app  
```
$ python wsgi.py
```
You can check in your web-browser that the application works by typing in address line of your browser:  

http://localhost:5000/  

## Upload a png-file  
```
$  curl -sF file=@"car.png" http://localhost:5000/documents
```
* Standard response returns a json file in the following format:  
  ```
  {
      "id": 1, 
      "tag": "car"
  }

## Get metadata  

```
curl -s http://localhost:5000/documents/1
```
  
## Get link   

```
$ curl -s http://localhost:5000/images/car
```