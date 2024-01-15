CRYPTO
#### Description: In this project I developed a simulated cryptocurrency trading application with similar techniques and knowledge from the previous problem set application called finance. I used most of the same code I wrote from the previous problem set except for a few exceptions and implementations, and created many more functions as well as followed a new API software. After hours of trying to find a perfect API I found one known as coinranking. I visited its website, created an account, generated an API key and followed .json notation to get the values of each cryptocurrency. I used the same layout and format from the previous problem set with the new functions “/ranking”, “/change_username”, “/change_password” and “/user”.

In “/ranking” I had 2 methods in which I tried and only one of them succeeded. In this function, we want to calculate a user’s current net worth and display the users in order based on that net worth. My first method was calculating the net worth in “/ranking” and passing it through a variable and displaying it in the html file, however I kept getting errors and was unable to fix it. Instead of calculating net worth that way, I calculated it again with a loop adding the price of each owned cryptocurrency multiplied with its quantity like the previous method but instead in the index function or “/” and adding it to the database for each user’s id. That way every time a user logs in their net worth will be updated or added if not already. Next, I pulled and ordered the net worths of all users, and its row number in descending order so that the first place user is on the top of the page. Next in the “ranking.html” file I used a loop to display the data in a table with headers.

I created a settings page with 2 functions, “/change_username” and “/change_password”. Each with an old password checker for security purposes. In “/change_username” the first step I did was to make sure that the inputs are all filled and that the inputs are not empty or null. Then once we first hash the “old_password” that the user inputted, we compare it to the hash of the password of the user when they first created their account or their current password’s hash. If they are the same then we continue, but if there is a difference an apology will be returned. Then we update the database of the specific user’s id with the new username they inputted. There are currently no restrictions on the username’s size, but I should put it into consideration to add it in the future.

The “/change_password” function does almost the exact same thing as “/change_password”, but instead of updating the username of a specific user id, it changes the password hash of a specific user id. We make sure that no inputs are null and that old password hash matches the user’s current password hash. If they match then we continue, but if not we return an apology. Now we update the current password hash held by the user in the database by generating the new password hash with the new password inputted by the user.

The “/user” function simply searches for a user’s username and displays their portfolio which consists of cryptocurrencies they own and the quantities just for a little competitiveness throughout the game. First I make sure the search bar for the username is not null. If it is null, we stop and return an apology, if it isn’t then we continue. Then based on the username inputted by the user we can find the username through the database since there is an index not allowing duplicate usernames. If it isn’t there, an error is returned, but if it is then we grab the cryptocurrency types and the quantities owned by the user into a variable as well as the username. Then in the html file we pass the variable data through a loop which outputs all of the stocks and the quantities owned by the user in a data table. Finally, we pass the username variable as a <h1> tag to make it clear that it is their portfolio.

That is my project, but I forgot to mention my database structure. It has 3 tables that are user, portfolio, and purchases. The fields in user are id, username, hash, cash, and net_worth. The id is where a distinct number for each user is present and auto increments for each user that registers a new account. The username field is where the user’s username they choose will be stored and the hash is where the password that the user chose is generated into a distinct hash, so not even me as the developer can hack into their accounts to ensure security. The cash field is where every time a user buys or sells a cryptocurrency the cash will be updated and is set to 10,000 at default, but may be subject to change. The net_worth field includes the cryptocurrency prices multiplied by their quantities and added to their current cash. In the portfolio table the fields are userid, stock, and quantity. The stock field is where cryptocurrencies are stored, but I couldn't change it to crypto or a more fitting name due to my progress in the project and how it would be ineffective to go back and change every word in my code. The quantity field is the quantity for each cryptocurrency and the userid is the id of the user's session. Finally, the purchases table has 5 fields. A userid field, stock field, price, quantity and BuyorSell. The userid field is also just the user’s session id, the stock field is the cryptocurrencies bought, the price is the price at which the cryptocurrency was bought or sold, the quantity field is the quantity of a cryptocurrency the user bought, and the BuyorSell field determines whether the transaction was a buy transaction or a sell transaction.
