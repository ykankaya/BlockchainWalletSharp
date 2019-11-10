# BlockchainWalletSharp
 An unofficial C# (.NET Core) library for interacting with the Blockchain.info Wallet API V2.

## Documentation
Example code for initializing a ``BlockchainWallet`` instance
```cs
var blockchainWallet = new BlockchainWallet(new Wallet
{
    Host = "http://127.0.0.1:3000",
    Identifier = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    Password = "xXxXxXxXxXxXxXxX"
});
```

Example code for sending a payment
```cs
var recipients = new Dictionary<string, long>
{
    { "1LaiteuxHEH4GsMC9aVmnwgUEZyrG6BiTH", 1337 }
};

var payment = blockchainWallet.PaymentAsync(recipients, feePerByte: 50).GetAwaiter().GetResult();

if (payment.Success)
{
    Console.WriteLine($"Payment successfully sent! TXID: {payment.TXID}");
}
else
{
    Console.WriteLine("An error occured while sending payment ...");
}
```

## Donate

If you like/use this library, please consider donating to support the project. Thank you!

### Bitcoin

- 1LaiteuxHEH4GsMC9aVmnwgUEZyrG6BiTH

## To-Do
- [ ] Handle Blockchain API errors & exceptions
