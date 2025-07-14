# 🚀 Node.js CI/CD Project with GitHub Actions and Heroku Deployment

Welcome to this practical project demonstrating how to implement a CI/CD pipeline using **GitHub Actions** and deploy a **Node.js** app to **Heroku**.

## 📚 Project Overview

This project is part of a CI/CD learning course focused on GitHub Actions and Heroku deployment. It includes:
- Automated build and test execution on every push to `main`
- Parallel build strategies using matrix builds
- Continuous deployment to Heroku on successful test runs

---

## 🛠️ Tech Stack

- **Node.js**
- **Express**
- **Mocha & Chai** (for testing)
- **GitHub Actions** (CI/CD)
- **Heroku** (hosting)

---

## 📁 Project Structure

my-project/
├── .github/
│ └── workflows/
│ └── deploy.yml
├── test/
│ └── app.test.js
├── index.js
├── server.js
├── package.json
├── README.md



---

## ⚙️ How It Works

### 1. **CI/CD Pipeline Setup**
The workflow file `.github/workflows/deploy.yml` defines steps:
- Checkout code
- Install dependencies
- Run tests (`npm test`)
- Deploy to Heroku if tests pass

### 2. **Heroku Deployment**
Deployment is handled using a Git push to Heroku via this command in the workflow:
```bash
git push https://heroku:${{ secrets.HEROKU_API_KEY }}@git.heroku.com/your-app-name.git HEAD:main
```


## 🚀 Deployment
🔐 Secrets Setup (on GitHub)
Go to your repo → Settings → Secrets and Variables → Actions

Add a secret:

HEROKU_API_KEY → Your Heroku API Key

🌐 Heroku Setup
Create a Heroku app:

bash
Copy
Edit
heroku create your-app-name
Confirm the remote:

bash
Copy
Edit
git remote -v




## ✅ Running Tests
We use Mocha and Chai for testing:

bash
Copy
Edit
npm test


- Sample test file is located at:

js

Copy

Edit

// test/app.test.js

import { expect } from 'chai';


describe('Sample Test', () => {
  it('should return true', () => {
    expect(true).to.be.true;
  });
});


## 🧪 GitHub Actions Workflow Example

yaml

Copy

Edit

name: Deploy to Heroku

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '16'

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test

      - name: Deploy to Heroku
        run: git push https://heroku:${{ secrets.HEROKU_API_KEY }}@git.heroku.com/your-app-name.git HEAD:main
🔍 Useful Commands

bash

Copy

Edit

heroku login

heroku create

heroku logs --tail

heroku open


## 📌 Notes

Ensure your app includes a start script in package.json:

json

Copy

Edit

"scripts": {

  "start": "node index.js",

  "test": "mocha"

}


You may optionally add a Procfile:

makefile

Copy

Edit

web: node index.js


![repo](image.png)

![cloned](image-1.png)

![commit](image-4.png)

![push](image-5.png)

![commit](image-2.png)

![build](image-3.png)

![success](image-6.png)

![index.js](image-7.png)

![server.js](image-8.png)

![package.json](image-9.png)

![apptest.json](image-11.png)

![npm test](image-12.png)

![npm ci](image-13.png)


![installation](image-14.png)

![installed](image-15.png)

![heroku](image-16.png)

![procfile](image-17.png)

![deployment yml](image-18.png)


![heroku appm creation](image-19.png)

![build](image-20.png)


![build success](image-21.png)

![git workflow deployment](image-22.png)

![yml update](image-23.png)

![log](image-24.png)

![access](image-25.png)

![hello world](image-26.png)

## ✨ Live Demo

#### 🌐 https://your-app-name.herokuapp.com

## 📄 License

This project is licensed under the MIT License.

