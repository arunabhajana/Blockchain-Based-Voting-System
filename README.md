
# Voting System Using Etherium BlockChain

A voting system using Ethereum blockchain, while promising in theory, faces challenges in real-world implementation. Issues such as scalability, high transaction costs, and complexity in smart contract development hinder its practicality. Additionally, ensuring voter privacy and security remains a concern, as blockchain transactions are transparent and irreversible. Regulatory hurdles and the need for widespread adoption further impede its effectiveness. Despite the potential benefits of transparency and decentralization, significant technical and societal challenges must be addressed before Ethereum-based voting systems can become viable alternatives to traditional methods




## Authors

- [@arunabhajana](https://github.com/arunabhajana)
- [@anirudh3369](https://github.com/anirudh3369)


##  Pre-Requisites

### Tech Stack
- node.js
- python
- html
- css
- mysql





## Screenshots

![App Screenshot](https://i.imgur.com/kPSxaxL.png)
![App Screenshot](https://i.imgur.com/V6RybSK.png)
![App Screenshot](https://i.imgur.com/abQBLy1.png)



## Demo

Video Demo For The Project : https://youtu.be/Lk9MfHaDBNA


## Deployment

1. Open a terminal.

2. Clone the repository by using the command
        
        git clone https://github.com/arunabhajana/Blockchain-Based-Voting-System

3. Download and install [Ganache](https://trufflesuite.com/ganache/).

4. Create a workspace named <b>developement</b>, in the truffle projects section add `truffle-config.js` by clicking `ADD PROJECT` button.

5. Download [Metamask](https://metamask.io/download/) extension for the browser.

6. Now create wallet (if you don't have one), then import accounts from ganache.

7. Add network to the metamask. ( Network name - Localhost 7575, RPC URl - http://localhost:7545, Chain ID - 1337, Currency symbol - ETH)

8. Open MySQL and create database named <b>voter_db</b>. (DON'T USE XAMPP)

9. In the database created, create new table named <b>voters</b> in the given format and add some values.

           CREATE TABLE voters (
           voter_id VARCHAR(36) PRIMARY KEY NOT NULL,
           role ENUM('admin', 'user') NOT NULL,
           password VARCHAR(255) NOT NULL
           );
   <br>

        +--------------------------------------+-------+-----------+
        | voter_id                             | role  | password  |
        +--------------------------------------+-------+-----------+
        |                                      |       |           |
        +--------------------------------------+-------+-----------+

12. Install truffle globally
    
        npm install -g truffle

14. Go to the root directory of repo and install node modules

        npm install

15. Install python dependencies

        pip install fastapi mysql-connector-python pydantic python-dotenv uvicorn uvicorn[standard] PyJWT

## Usage

#### Note: Update the database credentials in the `./Database_API/.env` file.

1. Open terminal at the project directory

2. Open Ganache and it's <b>development</b> workspace.

3. open terminal in project's root directory and run the command

        truffle console
   then compile the smart contracts with command

        compile

5. Bundle app.js with browserify
    
        browserify ./src/js/app.js -o ./src/dist/app.bundle.js

2. Start the node server server
    
        node index.js

3. Navigate to `Database_API` folder in another terminal
    
        cd Database_API
    then start the database server by following command

        uvicorn main:app --reload --host 127.0.0.1

4. In a new terminal migrate the truffle contract to local blockchain
    
        truffle migrate