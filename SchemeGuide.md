## OneWallet Scheme Guide


### Basic information

Onewallet URL Scheme starts with `onewallet://`, as shown in the following URL structure.

You can specify the type of feature in actionPath, and required parameters for each feature in `code={JSON DATA}`. Refer to the description of parameters for each feature, for more information.

<br>

### Add Card
Go to the automatically added card addition screen.

##### Action path
> input?code={JSON DATA}



##### JSON Key
| key | Type | Required | Description |
| ------ | ------ | ------ | ------ |
| code | String | Y |  CodeNumber | 
| walletType | Int | N(default = 0) |  WalletType(0 = Normal, 1 = Boarding Pass) |
| codeType | String | N(default = CODE_128) |  BarcodeType [CODE_128, CODE_39, CODE_93, PFD_417] | 
| qrType | String | N(default = QR_CODE) |  QRType [AZTEC, DATA_MATRIX, QR_CDOE] | 
| logoUrl | String | Y |  Logo Image Url | 
| backgroundColor | Int | N(default = 6710886) |  RGB(666666) or ARGB(FF666666) Integer Value | 
| title | String | Y |  Title | 
| subtitle | String | N |  SubTitle |
| extend1 | String(jsonString) | N(if wallet_type is 1(Boarding Pass) = Required Y) |  {\"key1\":\"title1 t\",\"value1\":\"value1 t\",\"key2\":\"title2 t\",\"value2\":\"value2 t\"} | 
| extend2 | String(jsonString) | N |  {\"key1\":\"title1 b\",\"value1\":\"value1 b\",\"key2\":\"title2 b\",\"value2\":\"value2 b\",\"key3\":\"title3 b\",\"value3\":\"value3 b\",\"key4\":\"title4 b\",\"value4\":\"value4 b\"} | 
| memo | String | N |  Memo | 
| expiredDate | Long | N |  Expried Timestamp | 



<br>
   
### Example


### Normal Type  

```
{ 
  "backgroundColor":-14649096,
  "code":"1234567890",
  "codeType":"CODE_128",
  "logoUrl":"https://lh3.googleusercontent.com/5MlRrSa9Wm47Ig9kd9mDD9J3ekq_Pj1LXqeEJ3korTCsrc2d68HBWJYNYs6_p_fMBw\u003ds128-rw",
  "memo":"memo",
  "qrType":"QR_CODE",
  "subtitle":"desc",
  "title":"title",
  "walletType":0
}
```

=> [onewallet://input?code=%7B++++%22backgroundColor%22:-14649096,+++%22code%22:%221234567890%22,+++%22codeType%22:%22CODE_128%22,+++%22logoUrl%22:%22https://lh3.googleusercontent.com/5MlRrSa9Wm47Ig9kd9mDD9J3ekq_Pj1LXqeEJ3korTCsrc2d68HBWJYNYs6_p_fMBw%5Cu003ds128-rw%22,+++%22memo%22:%22memo%22,+++%22qrType%22:%22QR_CODE%22,+++%22subtitle%22:%22desc%22,+++%22title%22:%22title%22,++++%22walletType%22:0+%7D](onewallet://input?code=%7B++++%22backgroundColor%22:-14649096,+++%22code%22:%221234567890%22,+++%22codeType%22:%22CODE_128%22,+++%22logoUrl%22:%22https://lh3.googleusercontent.com/5MlRrSa9Wm47Ig9kd9mDD9J3ekq_Pj1LXqeEJ3korTCsrc2d68HBWJYNYs6_p_fMBw%5Cu003ds128-rw%22,+++%22memo%22:%22memo%22,+++%22qrType%22:%22QR_CODE%22,+++%22subtitle%22:%22desc%22,+++%22title%22:%22title%22,++++%22walletType%22:0+%7D)

https://onewallet.kmshack.kr/sample1
  


### Boarding Pass Type  
```
{ 
  "backgroundColor":-12547848,
  "code":"1234567890",
  "codeType":"CODE_128",
  "expiredDate":1574953200000,
  "extend1":"{\"key1\":\"NYC\",\"value1\":\"New Yock City\",\"key2\":\"SFO\",\"value2\":\"San Francisco\"}",
  "extend2":"{\"key1\":\"Seat\",\"value1\":\"22A\",\"key2\":\"Flight\",\"value2\":\"475A\",\"key3\":\"Gate\",\"value3\":\"40A\",\"key4\":\"Boarding\",\"value4\":\"11:00 AM\"}",
  "logoUrl":"https://lh3.googleusercontent.com/rFdhVrgK0CY6dUL9wKIRIv2BU-fXnO7lNMbdHTRUk02tXuU6N1JlVJLTs9HwAE6tZ4Q\u003ds128-rw",
  "memo":"Memo",
  "qrType":"QR_CODE",
  "subtitle":"03 Feb",
  "title":"Passenger",
  "walletType":1
}

```

=> [onewallet://input?code=%7B++++%22backgroundColor%22:-12547848,+++%22code%22:%221234567890%22,+++%22codeType%22:%22CODE_128%22,+++%22expiredDate%22:1574953200000,+++%22extend1%22:%22%7B%5C%22key1%5C%22:%5C%22NYC%5C%22,%5C%22value1%5C%22:%5C%22New+Yock+City%5C%22,%5C%22key2%5C%22:%5C%22SFO%5C%22,%5C%22value2%5C%22:%5C%22San+Francisco%5C%22%7D%22,+++%22extend2%22:%22%7B%5C%22key1%5C%22:%5C%22Seat%5C%22,%5C%22value1%5C%22:%5C%2222A%5C%22,%5C%22key2%5C%22:%5C%22Flight%5C%22,%5C%22value2%5C%22:%5C%22475A%5C%22,%5C%22key3%5C%22:%5C%22Gate%5C%22,%5C%22value3%5C%22:%5C%2240A%5C%22,%5C%22key4%5C%22:%5C%22Boarding%5C%22,%5C%22value4%5C%22:%5C%2211:00+AM%5C%22%7D%22,+++%22logoUrl%22:%22https://lh3.googleusercontent.com/rFdhVrgK0CY6dUL9wKIRIv2BU-fXnO7lNMbdHTRUk02tXuU6N1JlVJLTs9HwAE6tZ4Q%5Cu003ds128-rw%22,+++%22memo%22:%22Memo%22,+++%22qrType%22:%22QR_CODE%22,+++%22subtitle%22:%2203+Feb%22,+++%22title%22:%22Passenger%22,+++%22walletType%22:1+%7D](onewallet://input?code=%7B++++%22backgroundColor%22:-12547848,+++%22code%22:%221234567890%22,+++%22codeType%22:%22CODE_128%22,+++%22expiredDate%22:1574953200000,+++%22extend1%22:%22%7B%5C%22key1%5C%22:%5C%22NYC%5C%22,%5C%22value1%5C%22:%5C%22New+Yock+City%5C%22,%5C%22key2%5C%22:%5C%22SFO%5C%22,%5C%22value2%5C%22:%5C%22San+Francisco%5C%22%7D%22,+++%22extend2%22:%22%7B%5C%22key1%5C%22:%5C%22Seat%5C%22,%5C%22value1%5C%22:%5C%2222A%5C%22,%5C%22key2%5C%22:%5C%22Flight%5C%22,%5C%22value2%5C%22:%5C%22475A%5C%22,%5C%22key3%5C%22:%5C%22Gate%5C%22,%5C%22value3%5C%22:%5C%2240A%5C%22,%5C%22key4%5C%22:%5C%22Boarding%5C%22,%5C%22value4%5C%22:%5C%2211:00+AM%5C%22%7D%22,+++%22logoUrl%22:%22https://lh3.googleusercontent.com/rFdhVrgK0CY6dUL9wKIRIv2BU-fXnO7lNMbdHTRUk02tXuU6N1JlVJLTs9HwAE6tZ4Q%5Cu003ds128-rw%22,+++%22memo%22:%22Memo%22,+++%22qrType%22:%22QR_CODE%22,+++%22subtitle%22:%2203+Feb%22,+++%22title%22:%22Passenger%22,+++%22walletType%22:1+%7D)


https://onewallet.kmshack.kr/sample2





