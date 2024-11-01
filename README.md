# dockerize-a-mern-stack-app
This repo helps you understand how to containerize a mern stack app and deploy

A simple MERN stack application
**Create a network for the docker containers**

docker network create demo

# **Build the client**

cd mern/frontend

<pre><code>docker build -t mern-frontend .</code></pre>

# **Run the client**

<pre><code>
docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend
</code></pre>

# **Verify the client is running**

Open your browser and type http://localhost:5173

# **Run the mongodb container**

<pre><code>
docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest
</code></pre>

# **Build the server**

<pre><code>
cd mern/backend
</code></pre>

<pre><code>
docker build -t mern-backend .
</code></pre>

# **Run the server**

<pre><code>
docker run --name=backend --network=demo -d -p 5050:5050 mern-backend
</code></pre>

# **Using Docker Compose**

<pre><code>
docker compose up -d
</code></pre>
