# QuantumPredict: Quantifying Forex Market Asymmetry for Algorithmic Trading

QuantumPredict is a sophisticated algorithmic trading platform designed to leverage statistical signal processing and backpropagation-optimized indicator fusion to quantify and exploit asymmetries within the Forex market. This project aims to identify subtle, non-random patterns in price action that are often overlooked by traditional technical analysis techniques. By combining advanced signal processing methodologies with a machine learning-driven approach to indicator weighting, QuantumPredict strives to generate robust and adaptive trading signals capable of consistently outperforming benchmark strategies. The platform provides a modular and extensible architecture, allowing developers to easily integrate custom indicators, risk management protocols, and execution strategies.

The core of QuantumPredict lies in its ability to analyze Forex time series data through the lens of non-linear dynamics. We employ techniques such as detrended fluctuation analysis (DFA), higher-order spectral analysis (HOSA), and wavelet transforms to extract features that characterize the degree of asymmetry and complexity present in price movements. These features are then fed into a backpropagation neural network that learns to optimally combine them with a diverse set of technical indicators, including moving averages, oscillators, and volatility measures. This fusion process allows the network to identify predictive relationships between market dynamics and future price movements, even in highly volatile and unpredictable conditions.

QuantumPredict offers a comprehensive suite of tools for backtesting, optimization, and real-time trading. The backtesting module allows users to evaluate the performance of different indicator combinations and trading strategies across historical datasets, providing detailed performance metrics such as Sharpe ratio, maximum drawdown, and win rate. The optimization module employs genetic algorithms to fine-tune the parameters of the neural network and the trading strategy, ensuring that the system remains adaptive to changing market conditions. The real-time trading module integrates with various Forex brokers via a standardized API, enabling automated execution of trading signals generated by the platform. The platform is built with scalability and performance in mind, allowing it to handle large volumes of data and execute trades with low latency.

## Key Features

*   **Statistical Signal Processing:** Implements advanced techniques like DFA, HOSA, and wavelet transforms for quantifying market asymmetry and non-linearity. Specifically, DFA is used to calculate the Hurst exponent, providing insights into the long-range correlations of price series, while HOSA identifies deviations from Gaussian noise, revealing the presence of higher-order statistical dependencies.
*   **Backpropagation-Optimized Indicator Fusion:** Employs a multi-layer perceptron neural network, trained via backpropagation, to dynamically weight and combine a diverse set of technical indicators. The network architecture is modular, allowing for the easy addition of new indicators and layers. Regularization techniques (L1/L2) are used to prevent overfitting.
*   **Comprehensive Backtesting Module:** Provides a robust backtesting environment for evaluating the performance of different trading strategies across historical data. Includes detailed performance metrics, such as Sharpe ratio, Profit Factor, and Maximum Drawdown, calculated using a vectorised approach for speed and efficiency.
*   **Genetic Algorithm Optimization:** Implements a genetic algorithm to automatically optimize the parameters of the neural network and the trading strategy, ensuring adaptability to changing market conditions. The algorithm includes crossover, mutation, and selection operators, with configurable parameters for population size, mutation rate, and selection pressure.
*   **Real-Time Trading Integration:** Integrates with various Forex brokers via a standardized API (e.g., FIX, REST), enabling automated execution of trading signals generated by the platform. The API is designed to be asynchronous and non-blocking, ensuring low-latency trade execution.
*   **Modular and Extensible Architecture:** The platform is designed with a modular architecture, allowing developers to easily add custom indicators, risk management protocols, and execution strategies. This modularity promotes code reusability and maintainability.
*   **Data Pipeline Integration:** Supports ingestion and processing of tick-by-tick and OHLCV data from various data sources. Includes data cleaning and pre-processing modules to handle missing data and outliers.

## Technology Stack

*   **TypeScript:** Primary programming language for building the platform due to its strong typing system, which enhances code maintainability and reduces runtime errors.
*   **Node.js:** Runtime environment for executing the TypeScript code, providing a non-blocking, event-driven architecture suitable for handling real-time data streams.
*   **TensorFlow.js:** JavaScript library for machine learning, used to implement the backpropagation neural network for indicator fusion and optimization.
*   **Technical Indicators Library (e.g., TA-Lib):** Provides a collection of common technical indicators, such as moving averages, oscillators, and volatility measures, used as inputs to the neural network. A typescript version is preferred.
*   **Data Visualization Libraries (e.g., Chart.js):** Used for visualizing backtesting results, performance metrics, and real-time trading activity.
*   **REST API Framework (e.g., Express.js):** Used to create a REST API for accessing the platform's functionality and integrating it with other systems.

## Installation

1.  **Clone the repository:**
    git clone https://github.com/jjfhwang/QuantumPredict.git

2.  **Navigate to the project directory:**
    cd QuantumPredict

3.  **Install dependencies:**
    npm install

4.  **Install typescript globally**
    npm install -g typescript

5.  **Compile the Typescript Code**
    tsc

## Configuration

1.  **Create a `.env` file** in the root directory of the project.

2.  **Define the following environment variables:**

    *   `BROKER_API_KEY`: Your Forex broker's API key.
    *   `BROKER_API_SECRET`: Your Forex broker's API secret.
    *   `DATA_SOURCE_URL`: URL of the data source for historical and real-time data.
    *   `DATABASE_URL`: URL of the database for storing backtesting results and model parameters.
    *   `TRADING_PAIR`: The Forex pair you wish to trade (e.g., EURUSD).
    *   `RISK_PERCENTAGE`: The percentage of your account balance you are willing to risk on each trade.

3.  **Configure the `config.ts` file** (located in the `src` directory) to customize the trading strategy parameters, neural network architecture, and backtesting settings.

## Usage

1.  **Run the backtesting module:**
    node dist/backtest.js --strategy=myStrategy --data=historicalData.csv

    Replace `myStrategy` with the name of your trading strategy and `historicalData.csv` with the path to your historical data file. The backtesting results will be stored in the database specified in the `.env` file.

2.  **Run the optimization module:**
    node dist/optimize.js --strategy=myStrategy

    This will run the genetic algorithm to optimize the parameters of the specified trading strategy. The optimized parameters will be stored in the database.

3.  **Run the real-time trading module:**
    node dist/trade.js

    This will start the real-time trading module, which will connect to your Forex broker via the API specified in the `.env` file and automatically execute trading signals generated by the platform.

## Contributing

We welcome contributions to QuantumPredict! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear, concise, and well-documented code.
4.  Write unit tests for your changes.
5.  Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/QuantumPredict/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for providing the tools and libraries that made this project possible. Special thanks to the developers of TensorFlow.js, TA-Lib, and Node.js.