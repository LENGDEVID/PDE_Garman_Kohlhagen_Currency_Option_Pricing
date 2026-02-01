# Glossary - Garman-Kohlhagen Currency Option Pricing

## Abbreviations and Acronyms

| Abbreviation | Full Form | Context |
|:-------------|:----------|:--------|
| **FX** | Foreign Exchange | Currency trading markets |
| **PDE** | Partial Differential Equation | Mathematical equation with multiple variables |
| **SDE** | Stochastic Differential Equation | Equation describing random processes |
| **ATM** | At-The-Money | Option where spot price equals strike price (S ≈ K) |
| **ITM** | In-The-Money | Call: S > K, Put: S < K (option has intrinsic value) |
| **OTM** | Out-of-The-Money | Call: S < K, Put: S > K (option has no intrinsic value) |
| **FTCS** | Forward-Time Central-Space | Explicit finite difference method |
| **BTCS** | Backward-Time Central-Space | Implicit finite difference method |
| **CN** | Crank-Nicolson | Implicit finite difference method (average of FTCS and BTCS) |
| **CFL** | Courant-Friedrichs-Lewy | Stability condition for numerical methods |
| **P&L** | Profit and Loss | Financial gain or loss from trading |
| **GMV** | Global Minimum Variance | Portfolio with lowest possible risk |
| **EOA** | Empirical Order of Accuracy | Measured convergence rate from numerical experiments |

## Mathematical Symbols

| Symbol | Full Name | Definition |
|:-------|:----------|:-----------|
| **S(t)** | Spot Price | Current exchange rate at time t |
| **K** | Strike Price | Agreed-upon exchange rate for the option |
| **τ (tau)** | Time to Maturity | Time remaining until option expiration (τ = T - t) |
| **T** | Maturity Date | Expiration date of the option |
| **r_d** | Domestic Interest Rate | Interest rate in the domestic currency |
| **r_f** | Foreign Interest Rate | Interest rate in the foreign currency |
| **σ (sigma)** | Volatility | Measure of how much the exchange rate fluctuates |
| **Δt (Delta t)** | Time Step | Size of time interval in numerical methods |
| **ΔS (Delta S)** | Spatial Step | Size of price interval in numerical grid |
| **W_t** | Wiener Process | Mathematical model of random motion (Brownian motion) |
| **N(·)** | Normal CDF | Cumulative Distribution Function of standard normal distribution |
| **n(·)** | Normal PDF | Probability Density Function of standard normal distribution |
| **d₁, d₂** | Auxiliary Variables | Intermediate calculations in Black-Scholes-type formulas |

## Technical Terms - Student-Friendly Definitions

### Financial Concepts

**Option**
> A contract giving the right (but not obligation) to buy or sell an asset at a predetermined price on or before a specific date. Think of it as "price insurance" for future transactions.

**Call Option**
> The right to BUY foreign currency at strike price K. You profit when the spot price goes UP above the strike.

**Put Option**
> The right to SELL foreign currency at strike price K. You profit when the spot price goes DOWN below the strike.

**Intrinsic Value**
> The profit you would make if you exercised the option RIGHT NOW. For calls: max(S - K, 0). For puts: max(K - S, 0).

**Time Value**
> The extra value beyond intrinsic value due to the possibility that the option could become more profitable before expiration. Time value = Option Price - Intrinsic Value.

**Strike Price (K)**
> The "locked-in" exchange rate you agreed to when buying the option. This is the price at which you can buy (call) or sell (put) the currency.

**Spot Price (S)**
> The current market exchange rate RIGHT NOW. This changes constantly based on market conditions.

**Volatility (σ)**
> How "jumpy" or unpredictable the exchange rate is. High volatility = big price swings = more valuable options (more chance of profit).

**Interest Rate Differential (r_d - r_f)**
> The difference between domestic and foreign interest rates. This affects the "drift" or expected direction of currency movement.

**Hedging**
> Reducing risk by taking offsetting positions. Like buying insurance to protect against unfavorable price movements.

**Delta Hedging**
> A strategy to eliminate directional risk by holding the right amount of the underlying currency to offset option price changes.

### The Greeks

**Delta (Δ)**
> How much the option price changes when the spot price moves by $1. Range: 0 to 1 for calls. Think of it as the "speed" of price change.

**Gamma (Γ)**
> How much Delta changes when the spot price moves. It measures the "curvature" or acceleration of option price changes. High gamma = Delta changes rapidly.

**Vega (ν)**
> How much the option price changes when volatility increases by 1%. High vega = very sensitive to market uncertainty.

**Theta (Θ)**
> How much the option loses value each day due to time passing. Usually negative (time decay). Think of it as the "cost of waiting."

**Rho (ρ)**
> How much the option price changes when interest rates change by 1%. Less important for short-term options.

### Mathematical Concepts

**Partial Differential Equation (PDE)**
> An equation involving rates of change with respect to multiple variables (e.g., time AND price). The Garman-Kohlhagen PDE describes how option value evolves.

**Stochastic Differential Equation (SDE)**
> An equation describing how something random (like exchange rates) changes over time. "Stochastic" = involving randomness.

**Brownian Motion / Wiener Process**
> A mathematical model of continuous random movement, like a particle jiggling in water. Used to model unpredictable price changes.

**Risk-Neutral Measure**
> A mathematical "world" where all assets earn the risk-free rate on average. Not the real world, but makes pricing easier!

**Itô's Lemma**
> A calculus rule for functions of random processes. It's like the chain rule, but for stochastic processes. Essential for deriving the PDE.

**No-Arbitrage Principle**
> The idea that you can't make risk-free profit from price differences. If you could, everyone would do it until prices adjust.

**Boundary Conditions**
> Rules specifying option values at the edges of our domain (e.g., when S = 0 or S = ∞, or at expiration T).

**Terminal Condition**
> The option value at expiration. For calls: max(S - K, 0). For puts: max(K - S, 0). This is where we start solving backward in time.

### Numerical Methods Concepts

**Finite Difference Method**
> A technique to solve PDEs by replacing continuous derivatives with discrete approximations on a grid. Like approximating a smooth curve with small straight line segments.

**Grid / Mesh**
> A set of discrete points in space and time where we calculate option values. Think of it as a spreadsheet with rows (prices) and columns (times).

**Explicit Method (FTCS)**
> Directly calculates future values from current values. Fast but can be unstable (blow up) if time steps are too large.

**Implicit Method (BTCS, CN)**
> Solves a system of equations to find future values. Slower per step but stable for any time step size.

**Stability**
> Whether small errors stay small (stable) or grow exponentially (unstable). Unstable methods produce garbage results.

**Convergence**
> As we make the grid finer (smaller Δt and ΔS), the numerical solution approaches the true analytical solution.

**Truncation Error**
> The error introduced by approximating derivatives with finite differences. Smaller grid spacing = smaller error.

**Order of Accuracy**
> How fast the error decreases as grid spacing shrinks. First-order: error ∝ Δt. Second-order: error ∝ (Δt)² (much better!).

**CFL Condition**
> A stability requirement for explicit methods: Δt must be small enough relative to ΔS. Named after Courant, Friedrichs, and Lewy.

**Tridiagonal Matrix**
> A matrix with non-zero elements only on three diagonals (main diagonal and one above/below). Arises naturally in finite difference methods and can be solved efficiently.

**Thomas Algorithm**
> An efficient method to solve tridiagonal systems. Much faster than general matrix inversion (O(n) vs O(n³)).

### Advanced Concepts

**Put-Call Parity**
> A relationship between call and put prices: C - P = S·e^(-r_f·τ) - K·e^(-r_d·τ). Prevents arbitrage opportunities.

**Von Neumann Stability Analysis**
> A mathematical technique to determine if a numerical method is stable by testing how Fourier modes (wave-like patterns) evolve.

**Amplification Factor (ξ)**
> In stability analysis, how much errors grow (or shrink) per time step. |ξ| ≤ 1 means stable.

**Courant Number / CFL Number (λ)**
> A dimensionless parameter λ = σ²S²Δt/ΔS² that determines stability for explicit methods. Must be ≤ 0.5 for FTCS.

**Unconditional Stability**
> A method that is stable for ANY time step size (BTCS and CN have this property). Very desirable for practical use!

**Second-Order Accuracy**
> Error decreases with the square of grid spacing. If you halve Δt, error drops by 4×. Much better than first-order (only 2× improvement).

**Garman-Kohlhagen Model**
> Extension of Black-Scholes to currency options, accounting for foreign interest rates. Published in 1983.

**Closed-Form Solution**
> An exact formula you can write down and compute directly (like the Garman-Kohlhagen formulas). Opposite of numerical approximation.

---

## Quick Reference: Common Notation Patterns

- **Subscripts (e.g., V_i^n)**: Position on grid. i = space index, n = time index
- **Superscripts in math (e.g., S²)**: Exponents (S squared)
- **Partial derivatives (∂V/∂S)**: Rate of change of V with respect to S, holding other variables constant
- **exp(-r·τ)**: Exponential function, same as e^(-r·τ), used for discounting future values
- **max(a, b)**: Maximum of a and b. Returns whichever is larger
- **O(Δt²)**: "Big O notation" - describes how error scales with grid size

---

## Tips for Understanding the Presentation

1. **Start with intuition**: Understand WHAT each concept means before diving into HOW to calculate it
2. **Follow the Greeks**: Delta, Gamma, Vega, Theta are your friends for understanding option behavior
3. **Stability matters**: An unstable numerical method is useless, no matter how fast
4. **CN is the winner**: Crank-Nicolson combines the best of both worlds (stable + accurate)
5. **Visualizations tell the story**: Pay attention to the plots - they show what the math means
6. **ATM is special**: Most action happens near the strike price (S ≈ K)

---

*This glossary is designed to accompany the "Garman-Kohlhagen European Currency Option Pricing" presentation.*
