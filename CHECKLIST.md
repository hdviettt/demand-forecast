# Demand Forecasting Methods

This is a learning roadmap, not a claim that one method will be best for every dataset. A model should be judged by forecasts on dates it did not train on, using the business's actual forecast horizon and score.

## Essential baselines

These simple forecasts give us a reference point. More complex models should earn their extra complexity by improving on them.

- [x] Naive forecast (repeat the latest observed value)
- [x] Seasonal naive forecast (repeat the value from the same weekday one week earlier)

## Classical statistical methods

- [x] Simple / weighted moving average
- [x] Exponential smoothing (ETS): level, trend, and seasonal variants as appropriate
- [x] ARIMA / seasonal ARIMA
- [x] ARIMAX / seasonal ARIMA with external predictors (for example known promotions and holidays)
- [x] Prophet (additive, regression-based time-series model; not a tree-based ML method)

## Machine learning

- [x] Tree-based ensembles
  - [x] XGBoost
  - [x] LightGBM

## Deep learning

These are usually global models: they learn shared patterns from many related series. They are not a like-for-like comparison when only one store's history is used.

- [ ] DeepAR (probabilistic autoregressive recurrent model)
- [ ] Temporal Fusion Transformer (TFT, multi-horizon global model)

## Method notes

This list is a useful first survey of major model families, but it is not exhaustive and no list is universally complete. For a responsible comparison, the two baselines and a time-ordered validation are essential additions to a list of named model families. Croston-style methods target intermittent demand, which is a different data shape from daily store revenue with weekly opening patterns; add them only when the target series actually has intermittent non-zero demand.

For the first Rossmann notebook comparison, methods will be evaluated on one example store over the exact dates represented in the supplied test file. DeepAR and TFT are documented as later global-model extensions, rather than included in this single-store benchmark. A later multi-store experiment should compare global methods on all stores using the same chronological backtest.
