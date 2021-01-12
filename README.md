
## Installation via Composer

```
composer require irakan/paylink
```

## Usage

```php

$client = new \Paylink\Client();
$client->setVendorId('4444');
$client->setVendorSecret('ABC');
$client->setPersistToken(false);
$client->setEnvironment('prod');

Or

$client = new \Paylink\Client([
	'vendorId'  =>  '4444',
	'vendorSecret'  =>  'ABC',
	'persistToken'  =>  true,
	'environment'  =>  'testing',
]);

 $data = [
            'amount' => 5,
            'callBackUrl' => 'https://www.example.com',
            'clientEmail' => 'test@gmail.com',
            'clientMobile' => '0500000000',
            'clientName' => 'Zaid Matooq',
            'note' => 'This invoice is for VIP client.',
            'orderNumber' => 'MERCHANT-ANY-UNIQUE-ORDER-NUMBER-123123123',
            'products' => [
                [
                    'description' => 'Brown Hand bag leather for ladies',
                    'imageSrc' => 'http://merchantwebsite.com/img/img1.jpg',
                    'price' => 150,
                    'qty' => 1,
                    'title' => 'Hand bag',
                ],
            ],
        ];
        
 
$response = $client->createInvoice($data); 
// Get the invoice url from the response
```
