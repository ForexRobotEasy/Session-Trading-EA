# Session Trading EA ReadMe

## Product Description
The Session Trading EA is an expert advisor developed by the Forex Robot Easy team. It is designed to trade the GBPUSD pair using a trend-following strategy. This code serves as a sample implementation of the strategy described in the product review available at [Forex Robot Easy - Session Trading EA Review](https://forexroboteasy.com/forex-robot-review/session-trading-ea-review-gbpusd-trend-follow-strategy/). Please note that ForexRobotEasy is not the official developer of this product, and to find the official developer, please refer to MQL5.

## Input Parameters
- MaxOrders: Maximum number of orders to open (default: 5)
- MinDeposit: Minimum deposit requirement (default: $250.0)
- LotsPerDeposit: Lots per $250 deposit (default: 0.01)

## Initialization Function
The `OnInit` function is responsible for initializing the expert advisor. It checks if the account balance meets the minimum deposit requirement and sets the trading session timing. If the requirements are not met or the trading session cannot be set, the initialization fails.

## Start Function
The `OnTick` function is executed on each tick of the market. It first checks if trading is allowed during the current session. If not, it returns. It then checks the number of open orders and if it exceeds the maximum allowed, it returns. Next, it calculates the available margin for opening a new order based on the deposit and lot size requirements. If the lot size is not within the allowed range, it returns. Finally, it applies a trend-following strategy based on the 50-period simple moving average (SMA) for the GBPUSD pair. If the current candle crosses above or below the moving average, a new order is opened accordingly.

## Deinitialization Function
The `OnDeinit` function is responsible for closing all open orders when the expert advisor is removed or the terminal is closed. It iterates through all open orders and checks if they belong to the current symbol and have a specific magic number. If so, the order is closed using a market order type. The result of the order closure is printed in the terminal.

## Usage
To use this expert advisor, follow these steps:
1. Set the desired input parameters (MaxOrders, MinDeposit, and LotsPerDeposit) according to your trading preferences.
2. Compile the code using the MQL5 compiler.
3. Attach the expert advisor to the GBPUSD chart on your MetaTrader platform.
4. Ensure that trading is allowed during the specified session timing.
5. Monitor the expert advisor's actions in the terminal and adjust the input parameters as needed.

For more detailed reviews and trading results of this product, please visit [Forex Robot Easy - Session Trading EA Review](https://forexroboteasy.com/forex-robot-review/session-trading-ea-review-gbpusd-trend-follow-strategy/). Please note that ForexRobotEasy is not the official developer of this product. We only provide a sample code that can work as described in this product. To find the official developer of this product, please refer to MQL5.
