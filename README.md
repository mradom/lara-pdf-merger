# lara-pdf-merger

Original written by http://pdfmerger.codeplex.com/team/view<br/>

###Update

Change parsers and use tcpdf, tcpdi and tcpdi_parser
  
## Installation

### Laravel 5.x:

Require this package in your composer.json and update composer.

    "codigitar/laravel-pdf-merger": "1.0.*",

After updating composer, add the ServiceProvider to the providers array in config/app.php

    Codigitar\LaravelPdfMerger\PdfMergerServiceProvider::class,

You can optionally use the facade for shorter code. Add this to your facades:

    'PdfMerger' => Codigitar\LaravelPdfMerger\Facades\PdfMerger::class,
    
## Using

```php

$pdf = new Codigitar\LaravelPdfMerger\PdfManage;

$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4');
$pdf->addPDF('samplepdfs/two.pdf', '1-2');
$pdf->addPDF('samplepdfs/three.pdf', 'all');

//You can optionally specify a different orientation for each PDF
$pdf->addPDF('samplepdfs/one.pdf', '1, 3, 4', 'L');
$pdf->addPDF('samplepdfs/two.pdf', '1-2', 'P);

$pdf->merge('file', 'samplepdfs/TEST2.pdf', 'P');

// REPLACE 'file' WITH 'browser', 'download', 'string', or 'file' for output options
// Last parameter is for orientation (P for protrait, L for Landscape). 
// This will be used for every PDF that doesn't have an orientation specified
```
