This package is based on Laravel Daily's Laravel Invoices. 

We tweaked this a little for a few internal projects and highly recommend using Laravel Daily's Package available at -[https://packagist.org/packages/laraveldaily/laravel-invoices][link-packagist]

## Available Methods
Almost every configuration value can be overrided dynamically by methods.

## Invoice
#### General
- addItem(InvoiceItem $item)
- addItems(Iterable)
- name(string)
- status(string) - invoice status [paid/due] if needed
- seller(PartyContract)
- buyer(PartyContract)
- setCustomData(mixed) - allows user to attach additional data to invoice
- getCustomData() - retrieves additional data to use in template
- template(string)
- logo(string) - path to logo
- getLogo() - returns base64 encoded image, used in template to avoid path issues
- filename(string) - overrides automatic filename
- taxRate(float)
- shipping(float) - shipping amount
- **totalDiscount(float) - If not provided calculates itself**
- **totalTaxes(float) - If not provided calculates itself**
- **totalAmount(float) - If not provided calculates itself**
- **taxableAmount(float) - If not provided calculates itself**

#### Serial number
- series(string)
- sequence(int)
- delimiter(string)
- sequencePadding(int)
- serialNumberFormat(string)
- getSerialNumber() - returns formatted serial number

#### Date
- date(Carbon)
- dateFormat(string) - Carbon format of date
- payUntilDays(int) - Days payment due since invoice issued
- getDate() - returns formatted date
- getPayUntilDate() - return formatted due date

#### Currency
- currencyCode(string) - EUR, USD etc.
- currencyFraction(string) - Cents, Centimes, Pennies etc.
- currencySymbol(string)
- currencyDecimals(int)
- currencyDecimalPoint(string)
- currencyThousandsSeparator(string)
- currencyFormat(string)
- getAmountInWords(float, ?string $locale) - Spells out float to words, second parameter is locale
- getTotalAmountInWords() - spells out total_amount
- formatCurrency(float) - returns formatted value with currency settings '$ 1,99'

#### File
- stream() - opens invoice in browser
- download() - offers to download invoice
- save($disk) - saves invoice to storage, use ->filename() for filename
- url() - return url of saved invoice
- toHtml() - render html view instead of pdf

## InvoiceItem
- title(string) - product or service name
- description(string) - additional information for service entry
- units(string) - measurement units of item (adds units columns if set)
- quantity(float) - amount of units of item
- pricePerUnit(float)
- discount(float) - discount in currency
- discountByPercent(float) - discount by percents discountByPercent(15) means 15%
- tax(float)
- taxByPercent(float)
- **subTotalPrice(float) - If not provided calculates itself**

## Testing

``` bash
$ composer test
```

## Security

If you discover any security related issues, please email support@manifestghana.com instead of using the issue tracker.

## Author

- [Johnson Sebire][link-author]

## License

GPL-3.0-only. Please see the [license file](LICENSE.md) for more information.

[link-author]: https://johnsonsebire.com
[link-packagist]: https://packagist.org/packages/laraveldaily/laravel-invoices
