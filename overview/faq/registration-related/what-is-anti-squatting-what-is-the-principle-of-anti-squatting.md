# What is anti-squatting? What is the principle of anti-squatting?

On a blockchain, all user actions are public and transparent. Therefore, when a user wants to register a certain .dao account, and the corresponding transaction is still in the memory pool and not packed into the block, other people are able to see what account the user wants to register. Other people can immediately issue a transaction with a higher network fee in an attempt to get miners to package the transaction first to grab the account. Then sell the account at a higher price to someone who really wants to sign up for it. Anti-jacking is about preventing this behavior as much as possible.\
\
The .dao contract requires a two-step process for registering a new account, corresponding to two transactions, to perfectly prevent the above-mentioned robocalls.\
\
Step1:Privately initiate the registration request: Hash the account to be registered with the registrant's public key, send the first transaction, and place this Hash on the blockchain\
\
Step2:The contract requires that the Hash has reached a mature state, i.e. the last transaction has been packed into the block and has reached a certain number of confirmations.\
\
