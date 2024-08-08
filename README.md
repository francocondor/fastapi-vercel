# FastAPI Vercel Deployment

This project demonstrates how to deploy a FastAPI application on Vercel.

## Requirements

- Python installed on your machine
- Account on [Vercel](https://vercel.com/)

## Project Setup

1. **Project Structure**:
    - Ensure your project has the following structure:
    ```
    ├── api
    │   └── main.py
    ├── requirements.txt
    └── vercel.json
    ```

2. **[`main.py`](./api/main.py "Go to definition") File**:
    - Your [`api/main.py`](./api/main.py "Go to definition") file should look like this:
    ```python
    from fastapi import FastAPI

    app = FastAPI()


    @app.get('/')
    async def health_check():
      return "The health check is successful v0.0.1!"
    ```

3. **[`requirements.txt`](command:_github.copilot.openSymbolFromReferences?%5B%22requirements.txt%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22e%3A%5C%5CPC%5C%5CDocuments%5C%5CProyectos%5C%5CPython%5C%5Cfastapi-vercel%5C%5CREADME.md%22%2C%22_sep%22%3A1%2C%22external%22%3A%22file%3A%2F%2F%2Fe%253A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22path%22%3A%22%2FE%3A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A16%2C%22character%22%3A8%7D%7D%5D%5D "Go to definition") File**:
    - Ensure you have a [`requirements.txt`](command:_github.copilot.openSymbolFromReferences?%5B%22requirements.txt%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22e%3A%5C%5CPC%5C%5CDocuments%5C%5CProyectos%5C%5CPython%5C%5Cfastapi-vercel%5C%5CREADME.md%22%2C%22_sep%22%3A1%2C%22external%22%3A%22file%3A%2F%2F%2Fe%253A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22path%22%3A%22%2FE%3A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A16%2C%22character%22%3A8%7D%7D%5D%5D "Go to definition") file with the necessary dependencies:
    ```
    fastapi
    uvicorn
    ```

4. **[`vercel.json`](command:_github.copilot.openSymbolFromReferences?%5B%22vercel.json%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22e%3A%5C%5CPC%5C%5CDocuments%5C%5CProyectos%5C%5CPython%5C%5Cfastapi-vercel%5C%5CREADME.md%22%2C%22_sep%22%3A1%2C%22external%22%3A%22file%3A%2F%2F%2Fe%253A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22path%22%3A%22%2FE%3A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A6%2C%22character%22%3A29%7D%7D%5D%5D "Go to definition") File**:
    - Configure the [`vercel.json`](command:_github.copilot.openSymbolFromReferences?%5B%22vercel.json%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22e%3A%5C%5CPC%5C%5CDocuments%5C%5CProyectos%5C%5CPython%5C%5Cfastapi-vercel%5C%5CREADME.md%22%2C%22_sep%22%3A1%2C%22external%22%3A%22file%3A%2F%2F%2Fe%253A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22path%22%3A%22%2FE%3A%2FPC%2FDocuments%2FProyectos%2FPython%2Ffastapi-vercel%2FREADME.md%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A6%2C%22character%22%3A29%7D%7D%5D%5D "Go to definition") file to tell Vercel how to deploy your application:
    ```json
    {
        "builds": [
            {
                "src": "api/main.py",
                "use": "@vercel/python"
            }
        ],
        "routes": [
            {
                "src": "/(.*)",
                "dest": "api/main.py"
            }
        ]
    }
    ```

## Deployment

You have two options to deploy your application:

5. **Option 1: Deploy using Vercel CLI**
    - Open your terminal, install Vercel CLI, and deploy your project:
    ```powershell
    npm i -g vercel
    vercel .
    ```

6. **Option 2: Deploy using Vercel web interface**
    - Go to [Vercel](https://vercel.com/).
    - Login or create an account if you don't have one.
    - Click on "New Project".
    - Select the GitHub repository with your project.
    - Select the Framework option: "Other".
    - Click on "Deploy".

## Possible Issue with Node.js Version

- Go to the Vercel web interface.
- Click on "Settings".
- Search for "Node.js Version" and change it to 18.x.
- Finally, repeat your deployment option.

That's it! You have successfully deployed your FastAPI application using Vercel.
