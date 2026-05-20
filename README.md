# Product Management API

A simple **Product Management** backend built with FastAPI, SQLAlchemy, and PostgreSQL. It comes with a plain HTML frontend index.html 
## What This Project Does

Stores products in a PostgreSQL database (id, name, description, price, stock)
Exposes a REST API to create, read, and delete products
Serves a browser-based UI index.html that talks to the API directly
## Project Structure
BASE/
├── app/
│   ├── main.py        
│   ├── models.py      
│   ├── schemas.py     
│   ├── database.py    
│   ├── routes.py      
│   ├── crud.py        
│   └── index.html     
├── Dockerfile         
└── requirements.txt   
## Requirements

Python 3.11
PostgreSQL running locally (or via Docker)
pip
## Setup & Running Locally
### 1. Clone / Extract the project

bash
unzip BASE.zip
cd BASE
### 2. Create a virtual environment and install dependencies

bash
python -m venv myenv
venv\Scripts\activate
pip install -r requirements.txt


### 3. Set up PostgreSQL



postgresql://postgres:postgres@127.0.0.1:5432/postgres


### 4. Run the server

bash
uvicorn app.main:app --reload

The API will be available at: `http://127.0.0.1:8000`

### 5. Open the frontend

Open `app/index.html` directly in your browser. It connects to `http://127.0.0.1:8000` 




## API Reference

Method  Endpoint                   Description              
-----------------------------------------------------------
POST    `/products`                Create a new product     
GET     `/products`                List all products        
GET     `/products/{product_id}`   Get a single product     
DELETE  `/products/{product_id}`   Delete a product         

 Swagger UI: `http://127.0.0.1:8000/docs`
## Dependencies

Package           Purpose                              
------------------------------------------------------
`fastapi`         Web framework                       
`uvicorn`         ASGI server to run FastAPI          
`sqlalchemy`      ORM for database interaction         
`psycopg2-binary` PostgreSQL driver                   
`pydantic`        Data validation via Python types     
