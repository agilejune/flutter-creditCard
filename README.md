# Flutter Credit Card

Flutter 包允许您通过卡片检测轻松实现信用卡的 UI。

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/e546818ff64e4883a18a920f6a1c091c)](https://www.codacy.com/app/reg_3/flutter_credit_card?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=simformsolutions/flutter_credit_card&amp;utm_campaign=Badge_Grade)

## 预览

![The example app running in Android](https://github.com/simformsolutions/flutter_credit_card/blob/master/preview/preview.gif)

## 安装

1. 添加对`pubspec.yaml`的依赖

    *在 pub.dartlang.org 上的“安装”选项卡中获取最新版本*
    
```dart
dependencies:
    flutter_credit_card: 0.1.1
```

2.  导入包
```dart
import 'package:flutter_credit_card/flutter_credit_card.dart';
```

3.  添加

*带所需参数*
```dart

    CreditCardWidget(
        cardNumber: cardNumber,
        expiryDate: expiryDate, 
        cardHolderName: cardHolderName,
        cvvCode: cvvCode,
        showBackView: isCvvFocused, //true when you want to show cvv(back) view
    ),
```    
*带可选参数*
```dart   
    CreditCardWidget(
        cardNumber: cardNumber,
        expiryDate: expiryDate,
        cardHolderName: cardHolderName,
        cvvCode: cvvCode,
        showBackView: isCvvFocused,
        cardbgColor: Colors.black,
        height: 175,
        textStyle: TextStyle(color: Colors.yellowAccent),
        width: MediaQuery.of(context).size.width,
        animationDuration: Duration(milliseconds: 1000),
        ),
``` 
3.  CreditCardForm 添加

```dart
    CreditCardForm(
      themeColor: Colors.red,
      onCreditCardModelChange: (CreditCardModel data) {},
    ),
```

## 本地化

要本地化文本字段提示和标签，请使用“LocalizedText”模型。

```dart
const LocalizedText localizedText = LocalizedText(
    cardNumberLabel: 'Kreditkartennummer',
    cardNumberHint: 'XXXX-XXXX-XXXX-XXXX',
    expiryDateLabel: 'Ablaufdatum',
    expiryDateHint: 'MM/JJ',
    cvvLabel: 'Kartenprüfnummer',
    cvvHint: 'XXX',
    cardHolderLabel: 'Karteninhaber',
    cardHolderHint: 'Max Mustermann',
);

return Column(
    children: <Widget>[
        CreditCardWidget(
            cardNumber: cardNumber,
            expiryDate: expiryDate,
            cardHolderName: cardHolderName,
            cvvCode: cvvCode,
            showBackView: isCvvFocused,
            localizedText: localizedText,
        ),
        Expanded(
        child: SingleChildScrollView(
            child: CreditCardForm(
                onCreditCardModelChange: onCreditCardModelChange,
                localizedText: localizedText,
            ),
        ),
    ],
);
```

＃＃ 如何使用
查看 [example](example) 目录中的 **example** 应用程序或 pub.dartlang.org 上的“示例”选项卡以获取更完整的示例。

## Credit

这个包的动画灵感来自这个[Dribbble](https://dribbble.com/shots/2187649-Credit-card-Checkout-flow-AMEX) 艺术.
