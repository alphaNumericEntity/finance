# finance in GoLang


## Summary

This go package aims to provide a go application with access to current and historical financial markets data in streamlined, well-formatted structures.



### Features

Description | Source
--- | ---
Quote(s) | Yahoo finance
Equity quote(s) | Yahoo finance
Index quote(s) | Yahoo finance
Option quote(s) | Yahoo finance
Forex pair quote(s) | Yahoo finance
Cryptocurrency pair quote(s) | Yahoo finance
Futures quote(s) | Yahoo finance
ETF quote(s) | Yahoo finance
Mutual fund quote(s) | Yahoo finance
Historical quotes | Yahoo finance
Options straddles | Yahoo finance



## Usage example

Library usage is meant to be very specific about the user's intentions.

### Quote
```go
q, err := quote.Get("AAPL")
if err != nil {
  
  panic(err)
}

// Success!
fmt.Println(q)
```

### Equity quote (more fields)
```go
q, err := equity.Get("AAPL")
if err != nil {
 
  panic(err)
}

// Success!
fmt.Println(q)
```

### Historical quotes (OHLCV)
```go
params := &chart.Params{
  Symbol:   "TWTR",
  Interval: datetime.OneHour,
}
iter := chart.Get(params)

for iter.Next() {
  fmt.Println(iter.Bar())
}
if err := iter.Err(); err != nil {
  fmt.Println(err)
}
```



Run all tests:

    go test ./...

Run tests for one package:

    go test ./equity

Run a single test:

    go test ./equity -run TestGet


- Big shoutout to Stripe and the team working on the [stripe-go][stripe] project, I took a lot of library design / implementation hints from them.
