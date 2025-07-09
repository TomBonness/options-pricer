Project: Option Pricing API

Core Stuff:
* Implement Black-Scholes and Monte Carlo pricers
* Only american options no foreign markets
* SIMD + multithreading for MC simulations.

API Layer:
* Wrap the pricer with API
* maybe fully in c++ with cpp-httplib or Crow
* maybe use something like node or flash so it's easier to deploy with AWS amplify

Build/Deploy:
* CMake project

🖥️ Frontend (React/Tailwind/etc):
Input Form:
* Option type, spot, strike, volatility, rate, time to maturity
Output:
* Price, delta/greeks
* Graph for price vs strike, price vs volatility (use a chart lib)
* Monte Carlo: histogram of paths or convergence plot

📡 Communication:
* Frontend sends JSON payload: { "type": "call", "spot": 100, "strike": 95, "vol": 0.2, ... }
* Backend responds with JSON: { "price": 7.82, "delta": 0.63, "std_error": 0.02 }

Extra Stuff:
* Add unit tests with Catch2
* Benchmark MC implementation with and without threading
* Add Redis(!!!) or memory cache for repeated queries
