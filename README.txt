WELCOME TO ELECTRONIC PORTFOLIO

(1)General Problem
    This program simulates an investment portfolio management system that handles simple buy, sell, update, and search functionalities for stocks and 
    mutual funds.
    One can practice trading strategies risk-free and have fun!

Software Functionalities:
    Buy Investments: Users can purchase stocks or mutual funds by specifying the asset type, symbol, name, quantity, and price.
    Sell Investments: Users can sell a certain quantity of their investments at a specified price.
    Update Investment Prices: Users can update the prices of all investments in their portfolio.
    Calculate Total Gain: The software calculates the total gain or loss of the portfolio based on its current price.
    Search Investments: Users can search for investments based on symbol, keywords in the name, and price ranges, or all of them combined. Uses hashmaps for 
    fastness.
    Save to file and load to files.
    This software makes portfolio management better, making a cumbersome and tedious process manageable through a few simple operations.

(2)Assumptions and Limitations
Assumptions:
    Unique and Correct Symbols: Every stock and mutual fund is uniquely identified by its symbol.
    Commission and Fees: Stocks have a commission of $9.99 for both buying and selling, while mutual funds don’t have a commission but have a $45 redemption 
    fee when sold.
    Input Validity: The software assumes that the user inputs valid data types. If the user enters invalid data types, Java may produce a runtime error.
    Case-Insensitive Symbols: The software assumes symbols are case-insensitive.
    No Database Used: The program relies on  text files for data storing and retreiving, which limits scalabnility and other capabilities..
    No Real-Time Updates: Since there is no database or API used, users must manually save and reload data at the start and end of each session, and prices 
    must be entered manually which is tedious.

Limitations:
    Hardcoded Fees: The program hardcodes the $9.99 commission for stocks and the $45 fee for mutual funds, which may not match different brokerage fees, 
    potentially resulting in inaccurate gain calculations.
    Manual Price Updates: Users must manually update stock or mutual fund prices.
    No check on whether the investment exists (requires api).
    Limited Investment Types: The program only handles stocks and mutual funds. Other types of investments (like bonds, ETFs, etc.) are not supported.
    Outdated GUI (java swing)..

(3)User Guide
    Make the Program:
    Environment: YOU NEED JDK version 8 or higher is installed. AND ALSO java 17.
    The jar file should already exist. If not:

    A. Compilation and Execution within terminal:
        Compilation: javac -d bin src/ePortfolio/*.java
        Execution: java -cp bin ePortfolio.GUI

    B. Creation of a new JAR file.
        First compile: javac -d bin src/ePortfolio/*.java
        create jar file: jar cfm ePortfolio.jar manifest.txt -C bin/ . resources/ lib/
        execute jar file: java -jar ePortfolio.jar OR simply double click the jar file.
    
    Note: for OPTION B make sure manifests.txt includes Main-Class: ePortfolio.GUI and has a newline after that. 


File Contents:

src contains all the .java files:
    Portfolio.java: Contains the Portfolio class with methods to manage investments.
    Main.java: Contains the main method for running the application.
    Stock.java: Defines the Stock class representing stock investments.
    MutualFund.java: Defines the MutualFund class representing mutual fund investments.
    Investment.java: A superclass for all types of investments, including stocks and mutual funds, to simplify code by reducing redundancy.
lib contains the file "investments.txt" for saving and retrieving user game information.
bin contains all the .class files.
resources contains images.


(4)Test Plan
    A. Welcome Page
        Start the program.
        Make sure the welcome message and instructions are visible.
        Check that the menu shows the following options:
            Buy Investment
            Sell Investment
            Update Investments
            Get Total Gain
            Search Investments
            Quit
        Click on the Quit option to make sure the program closes.
        The welcome page should also include a bar with current balance.
        On the bottom it should have a set new balance and reset game button. 

    B.  Buy Investment
        Select the Buy Investment option from the menu.
        Check that the following fields appear:
        Type (with a dropdown for "Stock" and "Mutual Fund").
        Symbol (text field).
        Name (text field).
        Quantity (text field).
        Price (text field).
        Make sure the default type is "Stock."
        Test the Reset button to ensure all fields are cleared.
        Enter valid and invalid values in the fields and press Buy:
        Check that valid inputs add or update the investment.
        Check that invalid inputs are handled.
        Check if you can add to either stock/mutual fund whatevers opposite after adding a symbol as either stock/mutual fund. It should not allow u. 
        For example, if u add mutual fund with name aapl, u cant add stock with same name aapl.

    C. Sell Investment
        Choose the Sell Investment option from the menu.
        Verify fields for:
        Symbol (text field).
        Quantity (text field).
        Test the Reset button to clear the fields.
        Enter valid and invalid values and press sell button:
        Valid inputs should reduce the investment quantity.
        Invalid inputs should show an error message in the text area.
        Try entering a higher quantity then what is held in the investment, an error should appear.

    D. Update Investments
        Choose the Update Investments option from the menu.
        Check the interface shows:
        Noneditable fields for Symbol and Name 
        An editable field for Price.
        Prev, Next, and Save buttons. (this should be disabled if no investments, next/prev only if only one investment)
        Navigate through investments using Prev and Next:
        Edit the price and press Save:
        Valid prices should update the investment and show details in the text area.
        Invalid prices or inputs should show an error message.

    E. Get Total Gain
        Choose the Get Total Gain option from the menu.
        Check that the total gain shows up in a noneditable field.
        Check that detailed gains for each investment are shown in a scrollable text area.
        If price not updated for bought price, then see if the redemmption fee (-45, mutual fund) or commission fee (-9.99 stocks) appear for total gain.

(5)Possible Improvements
    *Replace in-memory or file-based storage with a relational database, which can help with info retrieval, and storage, and can help with search functions 
    and other functions. 
    *User Interface Enhancements: Develop a more modern GUI using JavaFX or javascript or web-based interface to improve accessibility and user experience. 
    *Dynamic Fees and Commissions:  Because every brokerage has different rates we should not hardcode fees and have an option to set them. 
    *Real Data: use an api to fetch live stock/mutual fund prices, saving users from manually entering prices which is a hassle.
    *Expand Investment Types: maybe also  include other investments like bonds, ETFs, and cryptocurrencies. THere are many kind of investments
    *create a webapp with java spring boot. 

