# macro-dashboard

A trading terminal I built because I was tired of watching Fed liquidity on one tab, options flow on another, sector rotation on a third, and oil fundamentals somewhere else entirely. This pulls it all into one place.

Live at **[the-macro-dashboard.com](https://the-macro-dashboard.com)** — 60-minute guest session, no login required.

---

## What's in it

**Macro panel** — Fed net liquidity (RRP, TGA, SOMA), yield curve, M2, GDP nowcast, shadow rate, fear index. The stuff that drives the tape before most retail traders notice.

**Sector rotation** — Relative Rotation Graphs across all 11 GICS sectors. Useful for spotting early accumulation before it shows up in price action.

**Economic calendar** — FOMC, CPI, NFP, PCE, earnings. Each event ranked by historical market impact with consensus and deviation scoring.

**Options analysis** — GEX walls, IV/GEX 3D surface across strikes and expirations, Greek sensitivities, dealer positioning pressure maps.

**Ticker terminal** — FinBERT sentiment on earnings calls and SEC filings, unusual options flow detection, dark pool tape with directional bias.

**Oil terminal** — Cushing storage level from satellite imagery (Copernicus/Sentinel Hub), global tanker fleet tracking via live AIS feeds, chokepoint monitoring across Hormuz, Suez, and Bab-el-Mandeb.

**Insider terminal** — STOCK Act politician filings, Form 4 corporate insider tape, weekly research reports, situational flash alerts.

**Seasonality** — Historical volatility patterns for indices, commodities, FX, rates, and individual equities. Overlay multiple years to spot recurring setups.

**Live terminal** — Shannon Bands, Put/Call Ratio intraday trace, dealer delta positioning.

---

## Pricing

Free tier includes the macro panel, sector rotation, and economic calendar. Pro (€29.99/mo) unlocks everything else — options analysis, oil terminal, insider terminal, full seasonality, and the live terminal.

3-day free trial on Pro, cancel anytime.

---

## Stack

React + Vite on the frontend, FastAPI backend running on Gunicorn with uvloop, Supabase (Postgres) for persistence, Redis for caching and rate limiting.

On the data side: FRED for Fed and macro series, Charles Schwab and Tradier for options, Finnhub and FMP for equities, EIA for energy, Copernicus/Sentinel Hub for satellite imagery, and live AIS feeds for vessel tracking.

ML layer uses FinBERT for financial sentiment, XGBoost for realized volatility forecasting, scikit-learn PCA for macro regime detection, and OpenCV + Groq for processing the satellite imagery. Deployed on GCP, reverse-proxied through Caddy.

---

This repository doesn't contain source code — the platform is closed-source. For questions or partnerships: research@the-macro-dashboard.com
