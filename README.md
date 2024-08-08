# FastAPI deploy with Vercel

This is a guide on how to deploy a FastAPI application using Vercel.

## Prerequisites

Before getting started, make sure you have the following:

- Python installed on your machine
- Vercel account (sign up at https://vercel.com)

## Steps

1. Create a new directory "api" for your "main.py"
2. Write your FastAPI Code in "main.py"

```powershell
from fastapi import FastAPI

app = FastAPI()


@app.get('/')
async def health_check():
    return "The health check is successful v0.0.1!"
```

3. Create your requeriments.txt
```powershell
fastapi
uvicorn
```

4. Config a vercel.json
```powershell
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

5. To deploy you have 2 options
    5.1. Option 1: Deploy using Vercel CLI
        - Open your terminal, install npm and deploy vercel
        ```powershell
        npm i -g vercel
        vercel .
        ```
    5.2. Option 2: Deploy using Vercel web interface
        - Go to [Vercel](https://vercel.com/).
        - Login or create an account.
        - Click on "New Project".
        - Select your GitHub repository with your project.
        - Select Framework option: "Other".
        - Click on "Deploy".

6. Possible problem with node version
    - Go to Vercel web interface.
    - Click on "Settings".
    - Search for "Node.js Version" and change it to 18.x.
    - Finally, repeat your deploy option again.

That's it! You have successfully deployed your FastAPI application using Vercel.
