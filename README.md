<br/>
<p align="center">
    <a href="https://github.com/TerraMystics"><img src="logo.jpg" align="center" width=350/></a>
</p>

<p align="center">
A lightweight payment management library for terra ecosystem
</p>

<p align="center">
  <a href="https://github.com/TerraMystics/Terra.Dart.OnChainPayments/blob/main/LICENSE.md">
  <img alt="GitHub" src="https://img.shields.io/github/license/terra-money/terra.js">
  </a>

  <a href="https://pub.dev/packages/terra_dart_onchain_payments">
  <img alt="GitHub" src="https://img.shields.io/pub/v/terra_dart_onchain_payments">
  </a>
  
  
  <a href="https://pub.dev/packages/terra_dart_onchain_payments">
  <img alt="GitHub" src="https://img.shields.io/pub/likes/terra_dart_onchain_payments?color=red">
  </a>
</p>

<p align="center">
  <a href="https://docs.terra.money/"><strong>Explore the Docs »</strong></a>
  <br />
  <br/>
  <a href="https://github.com/TerraMystics/Terra.Dart.OnChainPayments/tree/main/example/terra_dart_example">Example App</a>
  ·
  <a href="https://github.com/TerraMystics/Terra.Dart.OnChainPayments/blob/main/README.md">API Reference</a>
  ·
  <a href="https://pub.dev/packages/terra_dart_onchain_payments">Pub Package</a>
  ·
  <a href="https://github.com/TerraMystics/Terra.Dart.OnChainPayments">GitHub</a>
</p>

Internally manages gas estimation required by the burn tax for successful transactions on the blockchain. Makes it easier for devs to get started with payments on the LUNC/LUNA Blockchains.

## Features

- **Written in Dart**, with type definitions
- Works with the Flutter & Dart Ecosystems, in the browser, and Mobile solutions for anyone building on the Terra Ecosystem
- Makes it easier to manage payments for anyone deploying to the app store

## Installation & Configuration

Grab the latest version off [Pub](https://pub.dev/packages/terra_dart_onchain_payments)

```sh
dart pub add terra_dart_onchain_payments
```

## Usage

This package can be used for Mobile & Web Developers, or SDK Developers looking to extend the Terra Platform

### Manage Payments

```dart

void verifyCustomerBalance() {
     // Recovery Words of the Customer wallet that will be making the payment
     String customerRecoveryWords = "notice oak worry limit wrap speak medal online prefer cluster roof addict wrist behave treat actual wasp year salad speed social layer crew genius";

     // Configure your PaymentManager
     // Set Blockchain to target (in this case Classic)
     var paymentsManager = PaymentsManager()
          .configureBlockchain(env: TerraEnvironment.classic)
          .configureBusinessWallet(
              businessWallet) // Configure your Business Wallet
          .configureCustomerWallet(
              customerRecoveryWords); // Configure the Customer Wallet

     var simulation = await paymentsManager.getTotalFundsInCustomerWallet();
  }
```

```dart
void processPaymentForTerra() {
     // Wallet where customer payments will be transferred to
     String businessWallet = "terra17lmam6zguazs5q5u6z5mmx76uj63gldnse2pdp";

     // Recovery Words of the Customer wallet that will be making the payment
     String customerRecoveryWords = "notice oak worry limit wrap speak medal online prefer cluster roof addict wrist behave treat actual wasp year salad speed social layer crew genius";

     // Configure your PaymentManager
     // Set Blockchain to target (in this case Classic)
     var paymentsManager = PaymentsManager()
          .configureBlockchain(env: TerraEnvironment.classic)
          .configureBusinessWallet(
              businessWallet) // Configure your Business Wallet
          .configureCustomerWallet(
              customerRecoveryWords); // Configure the Customer Wallet

     var simulation = await paymentsManager.simulateChargeCustomer(100);
}
```

## License

This software is licensed under the MIT license. See [LICENSE](https://github.com/TerraMystics/terra_dart_onchain_payments/blob/main/LICENSE) for full disclosure.

© 2022 TerraMystics.
