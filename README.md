# dogecoincr

Dogecoin - CR


```js
// https://www.coingecko.com/en/api (∞ r/m)
const DogeCoinToUsdUrl = 'https://api.coingecko.com/api/v3/simple/price?ids=dogecoin&vs_currencies=usd';
const DogeCoinToUsdRequest = await fetch(DogeCoinToUsdUrl);
const DogeCoinToUsdJson = await DogeCoinToUsdRequest.json();
const DogeCoinAsUsd = DogeCoinToUsdJson['dogecoin']['usd'];
```

```js
// https://www.exchangerate-api.com (1.5K r/m)
const UsdToCrcUrl = 'https://v6.exchangerate-api.com/v6/f6361892ec0d8f79b8d35424/pair/USD/CRC';
const UsdToCrcRequest = await fetch(UsdToCrcUrl);
const UsdToCrcJson = await UsdToCrcRequest.json();
const UsdAsCrc = UsdToCrcJson['conversion_rate'];
```

```js
// https://min-api.cryptocompare.com/documentation (100K/m, 250K/total)
const DogeToCrcUrl = 'https://min-api.cryptocompare.com/data/price?api_key=b038cc5af6a67b30a4251b19a93ddc622e6af3198453d6c911db29e8d60fb572&fsym=DOGE&tsyms=CRC,USD';
const DogeToCrcRequest = await fetch(DogeToCrcUrl);
const DogeToCrcJson = await DogeToCrcRequest.json();
const DogeAsCrc = DogeToCrcJson['CRC'];
const DogeAsUsd = DogeToCrcJson['USD'];
```

```js
// https://developers.coinbase.com/api/v2#get-spot-price
async function getPrice(baseAsset = 'BTC', quoteAsset = 'USD') {
  const BaseAsset = baseAsset;
  const QuoteAsset = quoteAsset;
  const CurrencyPriceUrl = `https://api.coinbase.com/v2/prices/${BaseAsset}-${QuoteAsset}/spot`;
  const CurrencyPriceRequest = await fetch(CurrencyPriceUrl);
  const CurrencyPriceJson = CurrencyPriceRequest.json();
  const CurrencyPrice = CurrencyPriceJson['data']['amount'];
  console.log(CurrencyPriceRequest);
}

getPrice('ETH', 'USD');
```
