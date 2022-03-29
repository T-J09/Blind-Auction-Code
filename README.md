# Blind-Auction-Code
Day 9 : 100 days of Python

from replit import clear

from art import logo
print(logo)

bid_info = {}

def find_highest_bidder(bidding_record):
    highest_bid = 0
    for bidder in bidding_record:
        bid_amount = bidding_record[bidder]
        if bid_amount > highest_bid:
            highest_bid = bid_amount
            winner = bidder
    print(f"The winner is {winner} with a bid of ${highest_bid}")
    
def collect_bid_info():
    name = input("What is your name: ")
    bid = int(input("Please enter bid amount: $"))
    bid_info[name] = bid
    any_other_bids = input("are there any other bidders? Type 'yes' or 'no' : ").lower()
    if any_other_bids == "yes":
        clear()
        collect_bid_info()
    elif any_other_bids == "no":
        find_highest_bidder(bid_info)
        #Using max() function:
            # winner = max(bid_info, key=bid_info.get) 
            # price = max(bid_info.values())
            # print(f"The winner is {winner} with a bid of ${price}")
collect_bid_info()
