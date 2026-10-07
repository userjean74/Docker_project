Node.js Docker Project
Project Structure
.idea/              # IDE configuration
node_modules/       # Installed npm dependencies
.dockerignore       # Files excluded from Docker image
Dockerfile          # Docker image configuration
index.js            # Main Node.js application
package.json        # Project configuration and dependencies
package-lock.json   # Locked dependency versions
README.md           # Project documentation

Setup
1. Initialize Node.js
npm init -y

2. Install dependencies
npm install


This creates node_modules/ and package-lock.json.

3. Create Docker files

.dockerignore

node_modules
.idea
.git


Dockerfile

FROM node:20

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "index.js"]

4. Run locally
node index.js

5. Build Docker image
docker build -t node-app .

6. Run Docker container
docker run -p 3000:3000 node-app


Open:

http://localhost:3000


node_modules/ and .idea/ should generally not be committed to Git.
