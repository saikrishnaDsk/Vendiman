# Team-Project-8

##Save the Vending Machine 
**1.	Problems and Goals:**<br />
There are more than 7 million vending machines serving people in the U.S. every day, and these add up to a market more than 8 billion dollars. However, seeing the desired item being out-of-stock is one of the most disappointing moment. In fact, vending machines being out-of-stock are estimated to be at least 3% in lost sales. Therefore, having an interactive web app that helps tracking the stock information becomes crucial to improve the business.

**2.	Abstract:** <br />
We will be building a web application that allows suppliers to better monitor their vending machines supplies. We will also provide several ways for suppliers to receive low stock alerts, including automatic stock updates API (for Internet connected vending machines) and a consumer updates flow that will allow consumers to upload a picture of the vending machine.

We'll also build an internal service for vending machines to talk to each other, so vending machines can better guide customers to nearby machines when it runs out of stock and the other machine still have that product in stock. 

**3.	Approach:** <br />
- Node.js server and PostgreSQL DB to store stock & user information.
- React front end with different view for consumers and suppliers.
- Deploy the app on AWS


**4.	Features:**  <br />
- **Supplier:** 
  - Manage all vending machines in one place
  - Aggregated stock and sales data to better predict future supplies
  - Integrate our API to their machines for automatically stock updates and nearby suggestion features
  - Receive notifications when stock is or will be running out of stock

- **Consumer:** 
  - Help improve the accuracy of stock information by uploading a picture of the machine.

- **Smart Machine:**
  - Be able to display nearby stock info directly on the machines if a requested product runs out but is available at other machines. 
  - Record climate infomation (temperature, precipitation) via on machine sensor and data from NOAA to observe relations and advice on stocking. 
  - Display customized ads when user make purchases


# Installations
## Prerequisites
- [nvm](https://nodejs.org/en/download/)
  - Make sure you update your environment variables
- node.js
  ```
  nvm install node // This should install v16
  ```
  - You can verify with `nvm ls` and make sure it's pointing to `v16.x.x`

## Other requirements
Once nvm and node has been installed and you have checked out the latest version of this repo, you can simply run 
```
npm install
```
to install all other requirements. 

# Development
## Setup
The following command will compile both client and server side code and spin up a server that serve the frontend code at `localhost:3000`
```
npm run dev
```
You should see some compiling messages in our console similar to below if everything compiles successfully:
```
Compiling client ...
Compiling server ...
client:
  3 assets
  55 modules
  client (webpack 5.61.0) compiled successfully in 6168 ms

server:
  3 assets
  29 modules
  server (webpack 5.61.0) compiled successfully in 5892 ms
Starting Node.js ...
Debugger listening on ws://127.0.0.1:9229/52509200-d710-486f-b6d5-b679ace76830
For help, see: https://nodejs.org/en/docs/inspector
Server running on http://localhost:3000
```

## Work Distribution
- Wen-hao
  - You can start from `client/components/Supplier` in the code. I've included a brief skeleton for components and styles
  - The corresponding landing page would be `localhost:3000/supplier`
- Saikrishna
  - You can start from `client/components/VendingMachine` in the code. I've included a brief skeleton for components and styles
  - The corresponding landing page would be `localhost:3000/vending`
- Teja
  - You can start from `server/vendingMachine`. There's a router that you can add more endpoints/methods to handle different requests
  - You can send **GET** request directly from browser to `localhost/api/vm` or subsequent entpoints, or use `curl -X POST -d some_data` from command line

## Knowledge Sharing
There's also a `shared` folder that is meant for the API between front/backend. It'll be
up to the pair to decide how they want to setup the communication