# Express cluster PoC

This PoC aims to test if express work well with built-in node cluster https://nodejs.org/api/cluster.html#cluster

## How to

You can try with any load testing tool. In the guide, we will use https://github.com/codesenberg/bombardier

1. Clone this repo and install dependencies.

   ```
   npm install
   ```

2. Strat the server

   ```
   npm start
   ```

   The output should be something like this. It means node cluster start with multiple workers.

   ```
   Primary 16743 is running
   Worker 16754 started
   Worker 16748 started
   Worker 16747 started
   Worker 16751 started
   ```

3. Load test with

   ```
    bombardier -c 125 -n 10000000 --print=i,r,p http://localhost:8000
   ```

4. Observe process via `Activity Monitor`
# express-cluster-poc
