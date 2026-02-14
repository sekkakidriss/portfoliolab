# PortfolioLab - Complete User Guide

## 🇦🇪 Next-Generation Portfolio Analysis Tool • Made in UAE

A futuristic, client-side portfolio analysis tool with 3D graphics, drag-and-drop interface, and intelligent bond calculations. **100% privacy-first** - all calculations happen in your browser.

## ✨ Key Features

### 1. **Multiple Asset Support**
- Upload **unlimited stocks** - add as many companies as you want
- Upload **unlimited commodities** - Gold, Silver, Oil, Copper, etc.
- Manage each asset individually with add/remove functionality

### 2. **Drag & Drop Interface**
- Drag files directly onto drop zones
- Click to browse traditional file picker
- Multiple file selection supported
- Beautiful visual feedback

### 3. **Intelligent Bond Calculations**
- **You only provide:** Coupon Rate and Maturity Date
- **Tool automatically calculates:**
  - Expected Return
  - Volatility (Standard Deviation)
  - Duration
  - Correlations with stocks and commodities

### 4. **3D Futuristic Design**
- Animated 3D particle background (Three.js)
- Cyberpunk/sci-fi aesthetic
- Neon color scheme (cyan, magenta, electric purple)
- Smooth animations and transitions
- **UAE-inspired logo** - Combines UAE flag colors with futuristic data visualization

## 📊 How Bond Calculations Work

### What You Need to Know (Simple!)

When buying government bonds, you typically have:
1. **Coupon Interest Rate** - The annual interest payment (e.g., 4%)
2. **Maturity Date** - When the bond matures (e.g., 10 years)
3. **Credit Rating** - Bond quality rating (AAA, AA, A, etc.)

That's it! The tool calculates everything else.

### What the Tool Calculates Automatically

#### 1. **Expected Return**
For government bonds trading near par value, the expected return is approximately equal to the coupon rate.

**Formula:**
```
Expected Return ≈ Coupon Rate
```

**Example:**
- Coupon Rate: 4%
- Expected Return: 4% annually

#### 2. **Volatility (Standard Deviation)**
Bond volatility is calculated using **Duration** and **Interest Rate Volatility**.

**Formula:**
```
Volatility = Duration × Interest Rate Volatility × Credit Rating Adjustment
```

**Duration Calculation:**
```
Duration = (1 - (1 + yield)^-n) / yield

Where:
- yield = Expected return (as decimal)
- n = Years to maturity
```

**Example:**
- 10-year bond with 4% yield
- Duration ≈ 8.11 years
- Interest Rate Volatility: 1% (typical for government bonds)
- Credit Rating AA: 1.1x adjustment
- **Volatility = 8.11 × 0.01 × 1.1 = 8.9%**

#### 3. **Duration**
Duration measures how sensitive the bond is to interest rate changes.

**Interpretation:**
- Higher duration = More sensitive to rate changes
- Duration of 8 years = 1% rate increase causes ~8% price decline

**Formula:**
```
Modified Duration = (1 - (1 + y)^-n) / y

Where:
- y = yield (as decimal)
- n = years to maturity
```

#### 4. **Correlations with Stocks and Commodities**
The tool calculates realistic correlations based on:

**Bond-Stock Correlation:**
- Government bonds typically have **low to negative correlation** with stocks
- "Flight to quality" effect: When stocks fall, investors buy bonds
- Typical range: -0.2 to +0.2
- Tool uses actual return data when available

**Bond-Commodity Correlation:**
- Typically **very low correlation**
- Bonds and commodities respond to different factors
- Typical range: -0.1 to +0.2

**Calculation Method:**
The tool analyzes the historical returns of your uploaded stocks and commodities, then applies realistic correlation patterns based on:
- Market stress indicators
- Economic cycles
- Historical bond behavior

### Credit Rating Impact on Volatility

Different credit ratings have different risk levels:

| Rating | Quality | Volatility Multiplier |
|--------|---------|----------------------|
| AAA | Highest | 1.0x (baseline) |
| AA | High | 1.1x |
| A | Upper Medium | 1.2x |
| BBB | Lower Medium | 1.4x |
| BB | Speculative | 1.8x |
| B | Highly Speculative | 2.2x |

**Example:**
- AAA bond, 10 years: 8.1% volatility
- BBB bond, 10 years: 11.3% volatility (1.4x adjustment)

## 🎯 How to Use

### Step 1: Add Your Stock Data

**Option A - Drag & Drop:**
1. Download stock data from [Dubai Financial Market (DFM)](https://www.dfm.ae/)
2. Drag the Excel/CSV file onto the stock drop zone
3. File is parsed instantly

**Option B - Click to Browse:**
1. Click "Add Stock" button
2. Select one or multiple files
3. Each stock appears in the list

**Supported formats:**
- Excel (.xls, .xlsx) - including HTML-formatted exports from DFM
- CSV files

**What you'll see:**
- Stock file name
- Number of data points loaded
- ✓ Status indicator
- Remove button

### Step 2: Add Your Commodity Data

**Same process as stocks:**
1. Download from [Investing.com Commodities](https://www.investing.com/commodities/)
2. Drag & drop or click "Add Commodity"
3. CSV files supported

**Multiple commodities:**
- Gold
- Silver
- Oil (Crude, Brent)
- Copper
- Any commodity from Investing.com

### Step 3: Enter Bond Information

**Only 3 simple inputs needed:**

1. **Bond Name/Type**
   - Example: "UAE 10-Year Government Bond"
   - Example: "US Treasury 5-Year Note"

2. **Coupon Interest Rate (%)**
   - The annual interest payment rate
   - Example: 4.0%
   - Find this in your bond prospectus or broker statement

3. **Years to Maturity**
   - How many years until the bond matures
   - Example: 10 years
   - Can use decimals (e.g., 7.5 years)

4. **Credit Rating (Optional)**
   - Select from dropdown: AAA, AA, A, BBB, BB, B
   - Default: AA
   - Affects volatility calculation

**The tool instantly shows:**
- ✅ Expected Return (calculated)
- ✅ Volatility/Standard Deviation (calculated)
- ✅ Duration (calculated)

**Note:** Correlations are calculated during portfolio analysis using your actual stock/commodity data.

### Step 4: Set Investment Amounts

1. **Select Currency:** AED, USD, EUR, or GBP

2. **Enter amounts for each asset:**
   - Bonds: How much to invest in bonds
   - Commodities: Total commodity allocation
   - Stocks: Total stock allocation

3. **Tool shows:**
   - Percentage allocation for each (auto-calculated)
   - Total portfolio value

4. **Set Risk-Free Rate:**
   - Used for Sharpe Ratio calculation
   - Default: 3.5%
   - Use your country's treasury bill rate

### Step 5: Analyze

Click the **"ANALYZE PORTFOLIO"** button.

The tool will:
1. Calculate returns from historical data
2. Compute bond characteristics
3. Determine correlations
4. Calculate all portfolio metrics
5. Generate visualizations

**Processing time:** 1-3 seconds

### Step 6: Review Results

**Summary Cards:**
- Total Portfolio Value
- Expected Annual Return
- Portfolio Risk (Standard Deviation)
- Sharpe Ratio with rating

**Asset Allocation Table:**
- Breakdown by asset class
- Amount, weight, return, volatility
- Individual Sharpe ratios
- Total portfolio row

**Risk Metrics:**
- Portfolio Standard Deviation
- **Bond Duration** (NEW!)
- Value at Risk (95% & 99%, monthly & annual)
- Portfolio Beta
- Maximum Drawdown estimate

**Correlation Matrix:**
- Shows how assets move together
- Values from -1 (opposite) to +1 (together)
- Lower correlations = better diversification

**Charts:**
- Doughnut chart: Asset allocation
- Line chart: Historical price performance (indexed to 100)

### Step 7: Export & Save

- **Download PDF:** Full report (coming soon)
- **Download Excel:** All data and calculations (coming soon)
- **New Analysis:** Start over with different assets

## 🎨 PortfolioLab Logo Design

The PortfolioLab logo uniquely combines UAE national identity with cutting-edge financial technology:

### Design Elements

**UAE Flag Colors:**
- 🔴 **Red** - Strength and courage
- 🟢 **Green** - Growth and prosperity  
- ⚪ **White** - Peace and honesty
- ⚫ **Black** - Strength and determination

**Futuristic Overlay:**
- 📈 **Cyan graph line** - Represents portfolio performance
- 💎 **Data points** - Individual assets in your portfolio
- ✨ **Animated effects** - Dynamic, living data visualization

**Symbolism:**
The logo merges traditional UAE values (represented by the flag) with modern financial innovation (the data graph), perfectly embodying the spirit of PortfolioLab - bringing world-class investment analysis to UAE investors.

**Files Included:**
- `portfoliolab-logo.svg` - Full logo with animations (200x200)
- `favicon.svg` - Browser tab icon (32x32)
- Embedded in HTML as inline SVG with live animations

---

## 📈 Understanding Your Results

### Expected Return
**What it means:**
The average annual return you can expect from your portfolio based on historical data and bond characteristics.

**Formula:**
```
Portfolio Return = (Weight_bonds × Return_bonds) + 
                   (Weight_commodities × Return_commodities) + 
                   (Weight_stocks × Return_stocks)
```

**Example:**
- 40% Bonds at 4% = 1.6%
- 30% Commodities at 6% = 1.8%
- 30% Stocks at 10% = 3.0%
- **Total Expected Return = 6.4%**

### Standard Deviation (Risk)
**What it means:**
How much your portfolio's returns typically vary from the average. Higher = more volatile.

**Formula:**
```
σ_portfolio = √(w₁²σ₁² + w₂²σ₂² + w₃²σ₃² + 
                2w₁w₂σ₁σ₂ρ₁₂ + 2w₁w₃σ₁σ₃ρ₁₃ + 2w₂w₃σ₂σ₃ρ₂₃)
```

**Key insight:**
Thanks to diversification and low correlations, portfolio risk is usually **lower** than the weighted average of individual asset risks.

### Sharpe Ratio
**What it means:**
Risk-adjusted return. How much extra return you get per unit of risk.

**Formula:**
```
Sharpe Ratio = (Portfolio Return - Risk-Free Rate) / Portfolio Std Dev
```

**Rating scale:**
- **Below 0:** Poor (losing money vs. risk-free investment)
- **0 to 1:** Fair
- **1 to 2:** Good
- **2 to 3:** Very Good
- **Above 3:** Excellent

**Example:**
- Return: 6.4%
- Risk-free rate: 3.5%
- Std Dev: 8.2%
- **Sharpe = (6.4% - 3.5%) / 8.2% = 0.35** (Fair)

### Value at Risk (VaR)
**What it means:**
The maximum loss you're likely to experience over a given time period, at a certain confidence level.

**95% Monthly VaR:**
"There's a 95% chance you won't lose more than X in any given month"
(Or: 5% chance of losing more than X)

**99% Annual VaR:**
"There's a 99% chance you won't lose more than Y in a year"
(Or: 1% chance of losing more than Y)

**Formula:**
```
VaR = -(Expected Return - Z-score × Std Dev) × Portfolio Value

Where Z-scores:
- 95% confidence: 1.645
- 99% confidence: 2.326
```

### Portfolio Beta
**What it means:**
How much your portfolio moves relative to the overall market.

**Interpretation:**
- **Beta = 1.0:** Moves exactly with the market
- **Beta < 1.0:** Less volatile than market (more stable)
- **Beta > 1.0:** More volatile than market (amplified moves)

**Your portfolio:**
Typically has beta around 0.3-0.6 due to bonds and commodities, making it much more stable than pure stock portfolios.

### Bond Duration
**What it means:**
Measures how sensitive your bonds are to interest rate changes.

**Interpretation:**
- Duration of 8 years = If interest rates rise 1%, bond price falls ~8%
- Longer bonds = Higher duration = More interest rate risk
- Shorter bonds = Lower duration = Less interest rate risk

**Use it for:**
- Assessing interest rate risk
- Deciding when to buy/sell bonds
- Portfolio rebalancing decisions

## 💡 Tips for Best Results

### File Selection
- **Use at least 30 days** of historical data (60-90 days preferred)
- **More data = Better accuracy** for return and volatility calculations
- **Match date ranges** between stocks and commodities when possible

### Bond Information
- **Government bonds:** Use AAA or AA rating
- **Corporate bonds:** Use appropriate rating (A, BBB, etc.)
- **Longer maturity = Higher volatility** (automatically calculated)
- **Check current market rates** for accurate coupon rate

### Diversification
- **Low correlations are good!** Aim for correlations below 0.5
- **Mix asset classes** for better risk-adjusted returns
- **Don't over-concentrate** - avoid putting >70% in one asset

### Risk Management
- **Check VaR numbers** - Can you afford the potential losses?
- **Review Sharpe Ratio** - Is the return worth the risk?
- **Monitor duration** - Are you comfortable with interest rate risk?

## 🔒 Privacy & Security

### Your Data is 100% Safe

**What stays on your device:**
- Uploaded files (stocks, commodities)
- All calculations and results
- Charts and visualizations

**What goes to servers:**
- Nothing. Zero. Nada.

**Technical Details:**
- Files are read using JavaScript FileReader API (browser-native)
- All parsing happens in your browser's memory
- Calculations use JavaScript math functions
- No network requests to upload data
- No cookies, analytics, or tracking

**Verification:**
Open your browser's Developer Tools (F12) → Network tab. You'll see no upload requests.

### Data Lifecycle

1. **Upload:** File read from your computer into browser memory
2. **Process:** JavaScript parses and calculates
3. **Display:** Results shown on your screen
4. **Close:** When you close the tab, everything is cleared

**Storage:** None. Files are processed in memory and discarded.

## 🚀 Deployment Instructions

### Option 1: Use Locally (Zero Setup)

1. Download `portfolio-analyzer-3d.html`
2. Double-click to open in browser
3. Start analyzing!

**No server, no installation, no setup.**

### Option 2: Deploy to GitHub Pages (Free)

```bash
# 1. Create repository on GitHub
# 2. Upload the HTML file
# 3. Go to Settings → Pages
# 4. Select 'main' branch
# 5. Your URL: https://yourusername.github.io/portfolio-analyzer/
```

### Option 3: Deploy to Netlify (Free + Fast)

1. Go to https://netlify.com
2. Drag and drop the HTML file
3. Get instant URL: `https://portfolio-xyz.netlify.app`

**Benefits:** Global CDN, auto HTTPS, custom domain support

### Option 4: Deploy to Vercel (Free)

```bash
npm i -g vercel
vercel
# Follow prompts
```

**All deployments are free with no ongoing costs.**

## 📊 Mathematical Formulas Reference

### Returns
```
Daily Return = (Price_t - Price_{t-1}) / Price_{t-1}
Annualized Return = Mean_daily × 252
```

### Volatility
```
Daily Std Dev = √(Σ(Return_i - Mean)² / n)
Annualized Volatility = Daily_StdDev × √252
```

### Portfolio Metrics
```
Portfolio Return = Σ(w_i × R_i)

Portfolio Variance = Σ_i Σ_j (w_i × w_j × σ_i × σ_j × ρ_{ij})

Sharpe Ratio = (R_p - R_f) / σ_p

Portfolio Beta = Σ(w_i × β_i)
```

### Bond Metrics
```
Duration = (1 - (1 + y)^-n) / y

Bond Volatility = Duration × Interest_Rate_Vol × Credit_Adjustment

Expected Return ≈ Coupon Rate (for bonds near par)
```

### Risk Measures
```
VaR_{95%} = -(E[R] - 1.645 × σ) × Portfolio_Value
VaR_{99%} = -(E[R] - 2.326 × σ) × Portfolio_Value

Max Drawdown ≈ -2 × σ_portfolio
```

## 🛠️ Troubleshooting

### "Libraries are still loading"
- **Wait 2-3 seconds** after page opens
- Look for loading message to disappear
- Slow internet? Wait a bit longer

### "No valid price data found"
- **Check file format:** Must be Excel (.xls, .xlsx) or CSV
- **Verify columns:** Need "Close", "Last", or "Price" column
- **Check for data:** Prices must be numbers, not text

### Files won't upload
- **Check file size:** Should be under 5MB
- **Verify format:** .xls, .xlsx, or .csv only
- **Try different browser:** Chrome, Firefox, Safari, Edge

### Calculations seem wrong
- **Need 30+ days** of data minimum
- **Check bond inputs:** Coupon rate and maturity realistic?
- **Verify dates overlap** between stock and commodity files

### Charts not showing
- **JavaScript enabled?** Check browser settings
- **Try refreshing** the page (F5)
- **Check console** for errors (F12 → Console tab)

### 3D background not appearing
- **WebGL support:** Modern browsers required
- **Hardware acceleration:** Enable in browser settings
- **Try different browser** if issues persist

## 📚 Additional Resources

### Where to Get Data

**Stocks (UAE):**
- [Dubai Financial Market (DFM)](https://www.dfm.ae/)
- [Abu Dhabi Securities Exchange (ADX)](https://www.adx.ae/)

**International Stocks:**
- Yahoo Finance
- Google Finance
- Your broker's export tool

**Commodities:**
- [Investing.com Commodities](https://www.investing.com/commodities/)
- [Kitco (Precious Metals)](https://www.kitco.com/)

**Bond Information:**
- Central Bank websites
- Your broker or bank
- Bond prospectus documents

### Learn More

**Portfolio Theory:**
- Modern Portfolio Theory (Markowitz)
- Capital Asset Pricing Model (CAPM)
- Efficient Frontier

**Bond Math:**
- Duration and Convexity
- Yield to Maturity
- Interest Rate Risk

**Risk Metrics:**
- Value at Risk (VaR)
- Sharpe Ratio
- Beta and Alpha

## ⚠️ Important Disclaimers

1. **Not Financial Advice:** This tool is for educational and informational purposes only.

2. **Past Performance:** Historical data doesn't guarantee future results.

3. **Estimates:** All calculations are estimates based on assumptions and historical patterns.

4. **Consult Professionals:** Always consult a licensed financial advisor before making investment decisions.

5. **No Liability:** The developer assumes no liability for investment decisions based on this tool.

6. **Bond Calculations:** While based on established financial formulas, results are approximations. Actual bond behavior may vary.

7. **Correlations:** Calculated correlations can change over time, especially during market stress.

## 🎯 What Makes This Tool Special

### 1. Intelligent Automation
- Automatically calculates bond metrics from simple inputs
- No need to know advanced bond mathematics
- Realistic correlation estimates

### 2. User-Friendly Design
- Drag & drop interface
- 3D futuristic aesthetic
- Clear explanations of all metrics

### 3. Privacy-First
- 100% client-side processing
- No data sent to servers
- No tracking or analytics

### 4. Professional Quality
- Industry-standard formulas
- Institutional-grade calculations
- Comprehensive risk analysis

### 5. Free Forever
- No subscription fees
- No hidden costs
- Deploy anywhere for free

---

**Built with:** HTML5, CSS3, JavaScript, Three.js, Chart.js, SheetJS, PapaParse

**License:** Free for personal and educational use

**Support:** Check console for errors, review this README, or check GitHub issues

---

🚀 **Ready to analyze your portfolio? Open the HTML file and start investing smarter!**
