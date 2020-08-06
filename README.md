contract MyToken {
/* This creates an array with all balances */

mapping (address => uint256) public balanceOf;

function MyToken() {
balanceOf[msg.sender] = 1000000;
/* Send coins */
function transfer(address _to, uint256 _value) {

/* Check if sender has balance and for overflows */

require(balanceOf[msg.sender] >= _value && balanceOf[_to] + _value >=

balanceOf[_to]);

/* Add and subtract new balances */

balanceOf[msg.sender] -= _value;

balanceOf[_to] += _value;

}

Share on TwitterShare on FacebookShare on Linkedin
DOWNLOAD
Step by Step: How to Create a Cryptocurrency
by Daniel Won
Semi-trilingual Korean-American guy who feels like knowing about crypto is like when Neo takes the red pill in the Matrix
Jan 27, 2020
in Cryptocurrency
In this article
Introduction
Business Considerations
How to Create Your Own Token
How to Create a New Cryptocurrency (not a Token)
Need Help? Pay Experts!
How to Create Your Own Cryptocurrency for Free
Conclusion
Introduction
So you’ve heard of Bitcoin, Ethereum, and maybe other cryptocurrencies that have taken the world by storm. You’re looking to get involved somehow… What if you created your own cryptocurrency?

It’s a radical idea - creating your own money - perhaps that’s why, as we mentioned in our future of cryptocurrency article, crypto was the best performing asset class of the 2010s. However, if you know how to create a cryptocurrency, your radical idea can become reality.


$1 of Bitcoin at the beginning of the 2010s turned into more than $90,000 by the end of the decade. While not every cryptocurrency fared as well, creating something of such extreme value is no longer out of reach.
How to Create a Cryptocurrency: Business Considerations
Before jumping right into the development of your own crypto, there are some key business-related decisions you’ll want to consider if you want your project to be more than just a fun project.

1. Define a purpose for your cryptocurrency
If you’re going to create a cryptocurrency, there should probably be a reason for its existence. Otherwise, what reason do people have to use it?

Nano is an example of a cryptocurrency with a strongly defined purpose - fast and feeless digital payments.

Once you have a purpose for your cryptocurrency, be sure to explain it in a white paper, along with other aspects of your project.

2. Consider the legal implications
As the blockchain space has grown, so has regulatory scrutiny of the space. You want to make sure that everything you’re doing is legal throughout the entire process by consulting with a legal professional.

3. Define a budget
Creating your own cryptocurrency is no easy task and will likely require some financial resources unless you can take care of things like development, documentation, and marketing yourself.

While costs vary from project to project, here is a rough estimate of what you can expect:

Category	Time	Cost
Legal Counsel	Ongoing	$20,000-$100,000+
Development	15 minutes - 6 months+	$0-$100,000+
Whitepaper and Other Documentation	1-2 weeks	$5,000-$7,000, or about $500/page
Security Audit	1 month	$3,000-$10,000+
Marketing Promotion	1 month - 3 months+	$10,000/week
Listing (on Sites that List New Projects)	1 month+	$10,000+
Of course, you can do this all yourself for free. However, if you don’t have the necessary expertise, know that sourcing it may cost you.

4. Hire a strong development team
Unless you’re developing your crypto yourself, you’re going to need strong developers to help bring your idea to life. This might be difficult since demand for blockchain developers is through the roof, while supply of skilled blockchain developers remains low. Nevertheless, finding the right team is crucial, since blockchains deal with peoples’ hard earned money and need to be technically sound.

5. Hire external auditors
Found the right developers to create your cryptocurrency? Again, since it’s peoples’ money on the line, you’ll want to double and triple check that your security is top notch. This is where external security audits come in.

MakerDAO, a project that has about $400 million of crypto locked in its smart contracts as of writing, regularly undergoes external security audits.


MakerDAO is the leading DeFi (decentralized finance) application and has seen the value in its ecosystem explode, making it a target for hackers. Image credit: DeFi Pulse
6. Promote your project!
Even though making your cryptocurrency might seem impossible in itself, remember that after you make it, you need to promote it! You could have the best project in the world but if no one knows about it, it’ll be hard to make progress and grow the network.

Press releases, social media - especially channels popular with the crypto community like Twitter, Telegram, Reddit, and Discord, and blogs are a good place to start.

7. Nurture and grow your community
After promoting your project, you need to make sure that you engage with and nurture your community. Answer their questions and provide updates on your progress. Many projects have community management teams for the sole purpose of growing a loyal user base. Your early adopters will become your biggest fans and marketers so don’t neglect them!

How to Create Your Own Token
So in the world of crypto, there are various types of crypto assets. But one distinction people often make is between cryptocurrencies or coins and crypto tokens. Cryptocurrencies or crypto coins are crypto assets that have their own blockchain, or record of transactions. Bitcoin is a prominent example.

Tokens, on the other hand, use another blockchain instead of their own. The most popular example of a token would be the ERC20 token, which are tokens that use the Ethereum (ETH) blockchain.

Why are some assets tokens and not cryptocurrencies or coins? Simply put, it’s a lot easier to build on an already built out platform than it is to build your own. Moreover, what some projects will do is start out on a platform like Ethereum, before migrating to their own blockchain.

This saves a lot of time and money in development costs and also lets a team gauge a project’s potential before investing more into the development of their own blockchain.


Tron (TRX) is an example of a cryptocurrency that started out as an ERC20 token before moving to its own blockchain.
While you can create tokens on various networks like Ethereum, NEO, and EOS, we’ll teach you how to create your own crypto token on Ethereum, since it’s the most popular platform for doing so. Moreover, if you get stuck, Ethereum has the biggest developer community and documentation, both of which can make the process easier.

1. Deploy a new smart contract
To get started creating your own token on Ethereum, download Mist, an Ethereum wallet that also lets you mine or develop Ethereum software, such as an ERC20 token.

Once you’ve downloaded and opened Mist, fund it with ETH by going to the “WALLETS” tab, click the “CONTRACTS” tab then click “Deploy New Contract”. Where it says “Select Contract to Deploy” click the dropdown menu and select “MyToken.”

Then, enter this code in the Solidity Contract Source Code field that shows up:

contract MyToken {
/* This creates an array with all balances */

mapping (address => uint256) public balanceOf;

}
“Mapping” in this instance links balances to addresses, which are in hexadecimal format (the uint256 part - e.g. 0xab7c74abC0C4d48d1bdad5DCB26153FC8780f83E). “Public” means that anyone will be able to see other address’ token balances.

2. Decide on a token supply
Under the code from above, add this to set a limit on the amount of tokens you will create:

function MyToken() {
balanceOf[msg.sender] = 1000000;

}
In the above example, the token supply is 1 million. However, you can of course set this to any number you like.

3. Enable sending of your token
Congratulations! After steps 1-2, you have a smart contract linked to a token. Just one problem - you can’t send the token anywhere!

To fix this, add this code to the bottom of the Solidity Contract Source Code field:

/* Send coins */
function transfer(address _to, uint256 _value) {

/* Check if sender has balance and for overflows */

require(balanceOf[msg.sender] >= _value && balanceOf[_to] + _value >=

balanceOf[_to]);

/* Add and subtract new balances */

balanceOf[msg.sender] -= _value;

balanceOf[_to] += _value;

}

This code allows sending of your token as well as adding tokens (to receiving addresses) and subtracting tokens (from sending addresses) as necessary. To prevent users from sending more tokens than they actually have, we’ve added a line of code that checks the sender’s balance for any overflows (in sendable amount).

4. Setting your token’s name, symbol, and decimal units
For some final touches add this code:

/* Initializes contract with initial supply tokens to the creator of the contract */
function MyToken(uint256 initialSupply, string tokenName, string tokenSymbol, uint8 decimalUnits) {
balanceOf[msg.sender] = initialSupply; // Give the creator all initial tokens

name = dreik; // Set the name for display purposes

symbol = drk; // Set the symbol for display purposes

decimals = decimalUnits; // Amount of decimals for display purposes

/* Notify anyone listening that this transfer took place */
Transfer(msg.sender, _to, _value);

Share on TwitterShare on FacebookShare on Linkedin
DOWNLOAD
Step by Step: How to Create a Cryptocurrency
by Daniel Won
Semi-trilingual Korean-American guy who feels like knowing about crypto is like when Neo takes the red pill in the Matrix
Jan 27, 2020
in Cryptocurrency
In this article
Introduction
Business Considerations
How to Create Your Own Token
How to Create a New Cryptocurrency (not a Token)
Need Help? Pay Experts!
How to Create Your Own Cryptocurrency for Free
Conclusion
Introduction
So you’ve heard of Bitcoin, Ethereum, and maybe other cryptocurrencies that have taken the world by storm. You’re looking to get involved somehow… What if you created your own cryptocurrency?

It’s a radical idea - creating your own money - perhaps that’s why, as we mentioned in our future of cryptocurrency article, crypto was the best performing asset class of the 2010s. However, if you know how to create a cryptocurrency, your radical idea can become reality.


$1 of Bitcoin at the beginning of the 2010s turned into more than $90,000 by the end of the decade. While not every cryptocurrency fared as well, creating something of such extreme value is no longer out of reach.
How to Create a Cryptocurrency: Business Considerations
Before jumping right into the development of your own crypto, there are some key business-related decisions you’ll want to consider if you want your project to be more than just a fun project.

1. Define a purpose for your cryptocurrency
If you’re going to create a cryptocurrency, there should probably be a reason for its existence. Otherwise, what reason do people have to use it?

Nano is an example of a cryptocurrency with a strongly defined purpose - fast and feeless digital payments.

Once you have a purpose for your cryptocurrency, be sure to explain it in a white paper, along with other aspects of your project.

2. Consider the legal implications
As the blockchain space has grown, so has regulatory scrutiny of the space. You want to make sure that everything you’re doing is legal throughout the entire process by consulting with a legal professional.

3. Define a budget
Creating your own cryptocurrency is no easy task and will likely require some financial resources unless you can take care of things like development, documentation, and marketing yourself.

While costs vary from project to project, here is a rough estimate of what you can expect:

Category	Time	Cost
Legal Counsel	Ongoing	$20,000-$100,000+
Development	15 minutes - 6 months+	$0-$100,000+
Whitepaper and Other Documentation	1-2 weeks	$5,000-$7,000, or about $500/page
Security Audit	1 month	$3,000-$10,000+
Marketing Promotion	1 month - 3 months+	$10,000/week
Listing (on Sites that List New Projects)	1 month+	$10,000+
Of course, you can do this all yourself for free. However, if you don’t have the necessary expertise, know that sourcing it may cost you.

4. Hire a strong development team
Unless you’re developing your crypto yourself, you’re going to need strong developers to help bring your idea to life. This might be difficult since demand for blockchain developers is through the roof, while supply of skilled blockchain developers remains low. Nevertheless, finding the right team is crucial, since blockchains deal with peoples’ hard earned money and need to be technically sound.

5. Hire external auditors
Found the right developers to create your cryptocurrency? Again, since it’s peoples’ money on the line, you’ll want to double and triple check that your security is top notch. This is where external security audits come in.

MakerDAO, a project that has about $400 million of crypto locked in its smart contracts as of writing, regularly undergoes external security audits.


MakerDAO is the leading DeFi (decentralized finance) application and has seen the value in its ecosystem explode, making it a target for hackers. Image credit: DeFi Pulse
6. Promote your project!
Even though making your cryptocurrency might seem impossible in itself, remember that after you make it, you need to promote it! You could have the best project in the world but if no one knows about it, it’ll be hard to make progress and grow the network.

Press releases, social media - especially channels popular with the crypto community like Twitter, Telegram, Reddit, and Discord, and blogs are a good place to start.

7. Nurture and grow your community
After promoting your project, you need to make sure that you engage with and nurture your community. Answer their questions and provide updates on your progress. Many projects have community management teams for the sole purpose of growing a loyal user base. Your early adopters will become your biggest fans and marketers so don’t neglect them!

How to Create Your Own Token
So in the world of crypto, there are various types of crypto assets. But one distinction people often make is between cryptocurrencies or coins and crypto tokens. Cryptocurrencies or crypto coins are crypto assets that have their own blockchain, or record of transactions. Bitcoin is a prominent example.

Tokens, on the other hand, use another blockchain instead of their own. The most popular example of a token would be the ERC20 token, which are tokens that use the Ethereum (ETH) blockchain.

Why are some assets tokens and not cryptocurrencies or coins? Simply put, it’s a lot easier to build on an already built out platform than it is to build your own. Moreover, what some projects will do is start out on a platform like Ethereum, before migrating to their own blockchain.

This saves a lot of time and money in development costs and also lets a team gauge a project’s potential before investing more into the development of their own blockchain.


Tron (TRX) is an example of a cryptocurrency that started out as an ERC20 token before moving to its own blockchain.
While you can create tokens on various networks like Ethereum, NEO, and EOS, we’ll teach you how to create your own crypto token on Ethereum, since it’s the most popular platform for doing so. Moreover, if you get stuck, Ethereum has the biggest developer community and documentation, both of which can make the process easier.

1. Deploy a new smart contract
To get started creating your own token on Ethereum, download Mist, an Ethereum wallet that also lets you mine or develop Ethereum software, such as an ERC20 token.

Once you’ve downloaded and opened Mist, fund it with ETH by going to the “WALLETS” tab, click the “CONTRACTS” tab then click “Deploy New Contract”. Where it says “Select Contract to Deploy” click the dropdown menu and select “MyToken.”

Then, enter this code in the Solidity Contract Source Code field that shows up:

contract MyToken {
/* This creates an array with all balances */

mapping (address => uint256) public balanceOf;

}
“Mapping” in this instance links balances to addresses, which are in hexadecimal format (the uint256 part - e.g. 0xab7c74abC0C4d48d1bdad5DCB26153FC8780f83E). “Public” means that anyone will be able to see other address’ token balances.

2. Decide on a token supply
Under the code from above, add this to set a limit on the amount of tokens you will create:

function MyToken() {
balanceOf[msg.sender] = 1000000;

}
In the above example, the token supply is 1 million. However, you can of course set this to any number you like.

3. Enable sending of your token
Congratulations! After steps 1-2, you have a smart contract linked to a token. Just one problem - you can’t send the token anywhere!

To fix this, add this code to the bottom of the Solidity Contract Source Code field:

/* Send coins */
function transfer(address _to, uint256 _value) {

/* Check if sender has balance and for overflows */

require(balanceOf[msg.sender] >= _value && balanceOf[_to] + _value >=

balanceOf[_to]);

/* Add and subtract new balances */

balanceOf[msg.sender] -= _value;

balanceOf[_to] += _value;

}

This code allows sending of your token as well as adding tokens (to receiving addresses) and subtracting tokens (from sending addresses) as necessary. To prevent users from sending more tokens than they actually have, we’ve added a line of code that checks the sender’s balance for any overflows (in sendable amount).

4. Setting your token’s name, symbol, and decimal units
For some final touches add this code:

/* Initializes contract with initial supply tokens to the creator of the contract */
function MyToken(uint256 initialSupply, string tokenName, string tokenSymbol, uint8 decimalUnits) {
balanceOf[msg.sender] = initialSupply; // Give the creator all initial tokens

name = tokenName; // Set the name for display purposes

symbol = tokenSymbol; // Set the symbol for display purposes

decimals = decimalUnits; // Amount of decimals for display purposes

}
It should be fairly self-explanatory but change tokenName, tokenSymbol, and decimalUnits to change your token’s name e.g. Bitcoin, token symbol e.g. BTC, and decimal places e.g. Bitcoin has 8 decimal places.

5. Create a token transfer event
Lastly, add this code to turn on a transfer event, which allows ETH wallets to know when transfers of your token take place:

event Transfer(address indexed from, address indexed to, uint256 value);
Also, add this code to the transfer function from step 3:

/* Notify anyone listening that this transfer took place */
Transfer(msg.sender, _to, _value);

Full transfer function including transfer notification code:

/* Send coins */
function transfer(address _to, uint256 _value) {

/* Check if sender has balance and for overflows */

require(balanceOf[msg.sender] >= _value && balanceOf[_to] + _value >= balanceOf[_to]);


/* Add and subtract new balances */

balanceOf[msg.sender] -= _value;

balanceOf[_to] += _value;


/* Notify anyone listening that this transfer took place */

Transfer(msg.sender, _to, _value);

}
