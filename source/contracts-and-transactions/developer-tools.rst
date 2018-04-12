.. _Developer Tools:

********************************************************************************
Developer Tools
********************************************************************************

Using truffle to deploy Smart Contracts (v0.6)
================================================================================

**1. Install truffle**

Truffle is a command line tool to compile, deploy, and test smart contracts on blockchain.
Before installing truffle, you want to install or upgrade the npm to the latest version.
To install npm, use the following command:

.. code:: js

    $ sudo apt-get install npm

To upgrade npm, use the following command

.. code:: js

    $ sudo npm i -g npm

Run npm to install truffle

.. code:: js

    $ sudo npm install -g truffle

.. note:: Here -g is for global install so that truffle can be run from any directory

**2. Use truffle tool**

Once truffle is installed, you can type truffle to see a list of commands and options.

Usage: truffle <command> [options]

.. code:: js

    Commands:

        init      Initialize new and empty Ethereum project
        compile   Compile contract source files
        migrate   Run migrations to deploy contracts
        deploy    (alias for migrate)
        build     Execute build pipeline (if configuration present)
        test      Run JavaScript and Solidity tests
        debug     Interactively debug any transaction on the blockchain (experimental)
        opcode    Print the compiled opcodes for a given contract
        console   Run a console with contract abstractions and commands available
        develop   Open a console with a local development blockchain
        create    Helper to create new contracts, migrations and tests
        install   Install a package from the Ethereum Package Registry
        publish   Publish a package to the Ethereum Package Registry
        networks  Show addresses for deployed contracts on each network
        watch     Watch filesystem for changes and rebuild the project automatically
        serve     Serve the build directory on localhost and watch for changes
        exec      Execute a JS module within this Truffle environment
        unbox     Download a Truffle Box, a pre-built Truffle project
        version   Show version number and exit

See more at http://truffleframework.com/docs

**3. Initiate, compile, and deploy a truffle project for Wanchain**

Make a truffle directory

.. code:: js

    $ mkdir  wanchain-example

Initialize the truffle project

    **3.1 Initiate**

    In the truffle project directory,execute:

    .. code:: js

        $ truffle init

    Once a truffle project is initialized, several directories will be created, including

        * **contracts** : where the source contracts are supposed to reside
        * **migrations** : where the deployment scripts are supposed to reside
        * **test** :  where the test files are supposed to reside
        * **build** : the contract compiled result will be put here, created after running truffle compile or truffle migrate.
        * **truffle-config.js** : The configuration file provides default setup parameters for the project
        * **truffle.js** : This provide truffle smart contract parameters
    
    The directory will be like below:

    .. image:: ../img/directory.png
       :width: 931px
       :height: 141px
       :scale: 100 %
       :alt: directory
       :align: center


    **3.2 compile**

    In the truffle project directory, execute the command:

    .. code:: js

        $ truffle compile

    If the compilation is successful, a build directory will be created and abi files will be generated under **build/contracts/** directory.These abi files can then be deployed as smart contract.


    **3.3 Config**

    Setup truffle.js file to specify the network setting etc.

    .. code:: js

        module.exports = {
            networks: {
                development: {
                    host: 'localhost',
                    port: 8545,
                    network_id: '*',
                    gas: 4000000,
                    gasPrice: 180e9,
                    // following address needed to be replaced with unlocked account on gwan node
                    from: '0x8f84573C8BaB4d56FDdB48cc792424E8816908fB' 
                }
            }
        }

    Add deploy script for contract in the directory migrations in the truffle project:

    Such as the deploy script name is 2_deploy_contracts.js which will deploy the contract PollApp.sol in the contract directory, the script will be as following:

    .. code:: js

        var PollApp = artifacts.require("./PollApp.sol");
        module.exports = function(deployer) {
            deployer.deploy(PollApp);
        };

    **3.4 start gwan node on local host**

    Run following command in the directory which include gwan

    .. code:: js 

        $ ./gwan --rpc --testnet --rpcapi eth,net,admin,personal,wan --verbosity=0 console

    In the gwan console to unlock a existing wanchain account in gwan node and make sure there are balance in the unlocked account, this account need to be same with the from address in the file truffle.js

    **3.5 deploy contracts**

    Execute command in the truffle project directory:

    .. code:: js

        $ truffle migrate --network development

    The result will be as following:

    .. image:: ../img/commandLine.png
       :width: 732px
       :height: 310px
       :scale: 100 %
       :alt: commandLine
       :align: center

**4. Test deployed smart contract**

    **4.1 test script**

    Truffle support test for the contract, the test script should put in the directory “test” in the truffle,the test script maybe look like this:

    .. code:: js

        var solc = require('solc');
        var Web3 = require('web3');

        const PollApp = artifacts.require('./PollApp.sol');

        contract('PollApp', ([owner]) => {
            let PollAppInstance;

            before('set up contract before test', async () => {
                await web3.personal.unlockAccount(owner, '****', 9999);
                
                //create instance
                PollAppInstance = await PollApp.new({from: owner});
            })
            
            it('test case - 001', async () => {
                await PollAppInstance.XXX()({ from: owner });
                assert.equal(..., ..., 'description...');
            })
        })

    **4.2 start test**

    In the directory of the truffle project, execute the command:

    .. code:: js

        $ truffle test
        or specify to execute one test script
        $ truffle test ./test/XXX.js

    This command will execute the test script in the directory “test” of truffle project. The result may look like this:

    .. image:: ../img/pollapp.png
       :width: 778px
       :height: 106px
       :scale: 100 %
       :alt: pollapp
       :align: center





