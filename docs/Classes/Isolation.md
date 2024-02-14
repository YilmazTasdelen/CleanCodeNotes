# Isolating from Change

 We learned in OO 101 that there are concrete classes, which contain implementation details (code), and abstract classes, which
represent concepts only. 

A client class depending upon concrete details is at risk when
those details change. We can introduce interfaces and abstract classes to help isolate the impact of those details.

Dependencies upon concrete details create challenges for testing our system. 

If we’re building a Portfolio class and it depends upon an external TokyoStockExchange API to derive the portfolio’s value, our test cases are impacted by the volatility of such a lookup.

Instead of designing Portfolio so that it directly depends upon TokyoStockExchange, we create an interface, StockExchange, that declares a single method:
```
public interface StockExchange {
 Money currentPrice(String symbol);
}
public class ColumnList {
 public ColumnList(Column[] columns)
 public String generate()
}

```

We design TokyoStockExchange to implement this interface. We also make sure that the constructor of Portfolio takes a StockExchange reference as an argument:

```
public Portfolio {
 private StockExchange exchange;
 public Portfolio(StockExchange exchange) {
 this.exchange = exchange;
 }
 // ...
}
```
Now our test can create a testable implementation of the StockExchange interface that emulates the TokyoStockExchange.