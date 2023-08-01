# Templates for invoice2data

templates.letpdf.com


## start

start with [letpdf/bash: bash.letpdf.com](https://github.com/letpdf/bash) 
```bash
git clone https://github.com/letpdf/bash.git
```
and clone inside the templates of invoices
```bash
git clone https://github.com/letpdf/templates.git
```

## Examples

    issuer: Amazon Web Services, Inc.
    keywords:
    - Amazon Web Services
    fields:
      amount: TOTAL AMOUNT DUE ON.*\$(\d+\.\d+)
      amount_untaxed: TOTAL AMOUNT DUE ON.*\$(\d+\.\d+)
      date: Invoice Date:\s+([a-zA-Z]+ \d+ , \d+)
      invoice_number: Invoice Number:\s+(\d+)
      partner_name: (Amazon Web Services, Inc\.)
    options:
      remove_whitespace: false
      currency: HKD
      date_formats:
        - '%d/%m/%Y'
    lines:
        start: Detail
        end: \* May include estimated US sales tax
        first_line: ^    (?P<description>\w+.*)\$(?P<price_unit>\d+\.\d+)
        line: (.*)\$(\d+\.\d+)
        last_line: VAT \*\*