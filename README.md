# Python auto trade bot v1 (built circa 2021)

This bot was built to enable developers a chance to interact with the specific libraries and develop their skills from the Ground floor. You will find different ways to optimize the code that you are able to view, and I look forward to witnessing if this code actually grows.

First to start, here are some details about the 'risk strategy.py' file: 

## Key Features

- Reads in risk parameters from `risk_params.json`
- Dynamically updates risk parameters based on profit/loss  
- Calculates position sizes based on current price and equity
- Validates trades against risk limits before placing orders
- Rebalances positions to maintain sector allocation limits
- Sends summary reports to Teams channel

## Main Components

- `RiskManagement` class:
  - `validate_trade` - Checks trades against risk limits
  - `calculate_quantity` - Computes position size for orders
  - `rebalance_positions` - Rebalances portfolio allocation
  - `update_risk_parameters` - Adjusts risk params based on PnL
  - `report_profit_and_loss` - Calculates total P&L
- Helper methods: 
  - `get_current_price` - Fetches latest price data
  - `send_teams_message` - Sends summary to Teams
- `PortfolioManager` class - Tracks portfolio holdings
- Alpaca API wrapper - Interfaces with brokerage

## Flow 

1. Initialize `RiskManagement` with Alpaca API and risk parameters
2. Before placing each order:
   - Calculate quantity using `calculate_quantity`
   - Validate trade with `validate_trade`
3. Periodically rebalance portfolio with `rebalance_positions`
4. Update risk parameters based on profit/loss 
5. Send summary report to Teams channel
