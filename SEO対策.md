# SEO対策・トラッキングコード追記メモ

このファイルは、重複を避けるために削除したSEO対策とトラッキングコードのメモです。
サイトを公開する際に、新しいURLに合わせて以下を追記してください。

## ⚠️ 重要事項

- **公開URLが決まったら、必ず全てのURLを新しいURLに変更してください**
- **Google Tag ManagerのIDは、新しいサイト用のIDを取得してください**
- **Google検証ファイルは、新しいファイル名で作成してください**

---

## 1. Google Tag Manager (GTM)

### 削除したコード

**`<head>`内に追加：**
```html
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-TFX9WK2F');</script>
<!-- End Google Tag Manager -->
```

**`<body>`直後に追加：**
```html
<!-- Google Tag Manager (noscript) -->
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-TFX9WK2F"
height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
<!-- End Google Tag Manager (noscript) -->
```

### 追記時の注意点

- **`GTM-TFX9WK2F` を新しいサイト用のGTM IDに変更してください**
- 元のサイト（https://mjs.main.jp/karustep-LP/）と同じIDを使うと、データが混在します
- Google Tag Managerで新しいコンテナを作成し、新しいIDを取得してください

---

## 2. Canonical URL

### 削除したコード

```html
<link rel="canonical" href="https://mjs.main.jp/karustep-LP/">
```

### 追記時の注意点

- **`href`属性のURLを新しいサイトのURLに変更してください**
- 例：`https://example.com/` や `https://mjs.main.jp/karustep-LP-as-subrecord/`
- 重複コンテンツを防ぐために重要です

---

## 3. OGP (Open Graph) メタタグ

### 削除したコード

```html
<!-- OGP Meta Tags -->
<meta property="og:title" content="カルステップ｜踏むだけだから、向き合える。医療支援AIシュライバー">
<meta property="og:description" content="フットスイッチ操作による医療支援AIシュライバー「カルステップ（karustep）」。足で踏むだけでハンズフリー録音・AI要約・自動転記。医師の理想の診察を実現します。">
<meta property="og:type" content="website">
<meta property="og:url" content="https://mjs.main.jp/karustep-LP/">
<meta property="og:image" content="https://mjs.main.jp/karustep-LP/img/ogp-img.jpg">
<meta property="og:site_name" content="カルステップ">
<meta property="og:locale" content="ja_JP">
```

### 追記時の注意点

- **`og:url` を新しいサイトのURLに変更してください**
- **`og:image` のURLも新しいサイトのURLに変更してください**
  - 例：`https://新しいドメイン.com/img/ogp-img.jpg`
- SNSでシェアされた際に正しい情報が表示されます

---

## 4. Twitter Card メタタグ

### 削除したコード

```html
<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="カルステップ｜踏むだけだから、向き合える。医療支援AIシュライバー">
<meta name="twitter:description" content="フットスイッチ操作による医療支援AIシュライバー「カルステップ（karustep）」。足で踏むだけでハンズフリー録音・AI要約・自動転記。医師の理想の診察を実現します。">
<meta name="twitter:image" content="https://mjs.main.jp/karustep-LP/img/ogp-img.jpg">
```

### 追記時の注意点

- **`twitter:image` のURLを新しいサイトのURLに変更してください**
- Twitterでシェアされた際に正しい画像が表示されます

---

## 5. 構造化データ（JSON-LD）

### 削除したコード

```html
<!-- 構造化データ（JSON-LD） -->
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "Product",
    "name": "カルステップ",
    "alternateName": "karustep",
    "description": "フットスイッチ操作による医療支援AIシュライバー「カルステップ（karustep）」。足で踏むだけでハンズフリー録音・AI要約・自動転記を実現し、医師の理想の診察をサポートします。",
    "image": [
        "https://mjs.main.jp/karustep-LP/img/karustep-logo-with-title.png",
        "https://mjs.main.jp/karustep-LP/img/item1_foot_pedal.jpg",
        "https://mjs.main.jp/karustep-LP/img/item2_microphone.png",
        "https://mjs.main.jp/karustep-LP/img/after-using-karustep.jpg"
    ],
    "brand": {
        "@type": "Brand",
        "name": "カルステップ"
    },
    "offers": {
        "@type": "Offer",
        "price": "55,000",
        "priceCurrency": "JPY",
        "availability": "https://schema.org/InStock",
        "url": "https://buy.stripe.com/8x228r36d6Gdeg9dTd7ok03",
        "priceValidUntil": "2025-12-31",
        "hasMerchantReturnPolicy": {
            "@type": "MerchantReturnPolicy",
            "applicableCountry": "JP",
            "returnPolicyCategory": "https://schema.org/MerchantReturnFiniteReturnWindow",
            "merchantReturnDays": 30,
            "returnMethod": "https://schema.org/ReturnByMail",
            "returnFees": "https://schema.org/ReturnFeesCustomerResponsibility"
        },
        "shippingDetails": {
            "@type": "OfferShippingDetails",
            "shippingRate": {
                "@type": "MonetaryAmount",
                "value": "0",
                "currency": "JPY"
            },
            "shippingDestination": {
                "@type": "DefinedRegion",
                "addressCountry": "JP"
            },
            "deliveryTime": {
                "@type": "ShippingDeliveryTime",
                "handlingTime": {
                    "@type": "QuantitativeValue",
                    "minValue": 1,
                    "maxValue": 3,
                    "unitCode": "DAY"
                },
                "transitTime": {
                    "@type": "QuantitativeValue",
                    "minValue": 2,
                    "maxValue": 5,
                    "unitCode": "DAY"
                }
            }
        }
    },
    "category": "医療機器・医療システム",
    "audience": {
        "@type": "PeopleAudience",
        "audienceType": "医師・医療従事者"
    }
}
</script>
```

### 追記時の注意点

- **`image` 配列内の全てのURLを新しいサイトのURLに変更してください**
  - 例：`https://新しいドメイン.com/img/karustep-logo-with-title.png`
- 検索エンジンが商品情報を正しく理解するために重要です
- Google検索結果にリッチスニペットが表示される可能性があります

---

## 6. Google検証ファイル

### 削除したファイル

- `google554f8ae453ec332a.html`

### 追記時の注意点

- Google Search Consoleで新しいサイトを登録する際に、新しい検証ファイル名が表示されます
- そのファイル名でHTMLファイルを作成し、ルートディレクトリに配置してください
- ファイル内容は `google-site-verification: [ファイル名]` の形式になります

---

## 7. Google Clarity（もし使用している場合）

### 確認事項

元のサイトでGoogle Clarityを使用している場合は、以下を確認してください：

- 新しいサイト用にClarityプロジェクトを作成する
- 新しいプロジェクトのトラッキングコードを取得する
- 元のサイトと同じプロジェクトIDを使わない

---

## 追記手順のチェックリスト

- [ ] 公開URLを決定する
- [ ] Google Tag Managerで新しいコンテナを作成し、新しいIDを取得する
- [ ] Google Search Consoleで新しいサイトを登録する
- [ ] 新しい検証ファイルを作成する
- [ ] 全てのURL（canonical、OGP、構造化データ）を新しいURLに変更する
- [ ] 画像URLも新しいURLに変更する
- [ ] 動作確認を行う

---

## 参考リンク

- [Google Tag Manager](https://tagmanager.google.com/)
- [Google Search Console](https://search.google.com/search-console)
- [構造化データ テストツール](https://search.google.com/test/rich-results)
- [OGPデバッガー](https://developers.facebook.com/tools/debug/)

