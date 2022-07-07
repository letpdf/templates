# Templates for invoice2data

templates.letpdf.com

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