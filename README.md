# Table of contents

- [Table of contents](#table-of-contents)
- [PostFinance Checkout Android Payment SDK](#postfinance-checkout-android-payment-sdk)
  - [Installation](#installation)
- [PostFinance Checkout Android SDK — Migration Guide v2.0.0](#postfinance-checkout-android-sdk--migration-guide-v200)
  - [Requirements](#requirements)
  - [Installation](#installation-1)
  - [What's new](#whats-new)
  - [Breaking change — Entry class renamed](#breaking-change--entry-class-renamed)
  - [Migration](#migration)
    - [1. Update the import](#1-update-the-import)
    - [2. Update initialization](#2-update-initialization)
  - [Summary](#summary)
  - [Documentation](#documentation)

# PostFinance Checkout Android Payment SDK

[![Maven Central](https://img.shields.io/maven-central/v/ch.postfinance/postfinance-checkout-sdk)](https://central.sonatype.com/artifact/ch.postfinance/postfinance-checkout-sdk/1.5.2)

## Installation

# PostFinance Checkout Android SDK — Migration Guide v2.0.0

## Requirements

|                             | Version |
| --------------------------- | ------- |
| Kotlin                      | 2.1.20  |
| Android Gradle Plugin (AGP) | 8.7.0   |

## Installation

Latest version: **2.0.0** — [Maven Central](https://central.sonatype.com/artifact/ch.postfinance/postfinance-checkout-sdk)

Add the dependency to your `build.gradle.kts`:

```kotlin
implementation("ch.postfinance:postfinance-checkout-sdk:2.0.0")
```

---

## What's new

Version 2.0.0 brings a complete architectural overhaul of the SDK. The public API and component behavior remain unchanged — the only breaking change is the **entry class rename**.

The architecture has also been updated to comply with the **Android 16KB page size alignment requirement**, ensuring compatibility with devices running on 16KB memory page sizes as required by Google. For more details, see the [official Android documentation](https://developer.android.com/guide/practices/page-sizes).

> **Still seeing 16KB alignment issues in your app?**
> The problem may be caused by other libraries or an outdated build toolchain in your project. We recommend upgrading to **AGP 8.7.0 or higher** and updating your other dependencies to their latest versions.

---

## Breaking change — Entry class renamed

The main entry class has been renamed:

| v1.x                     | v2.0.0                |
| ------------------------ | --------------------- |
| `PostFinanceCheckoutSdk` | `PostFinanceCheckout` |

Update your import and all references accordingly.

---

## Migration

### 1. Update the import

```kotlin
// Before
import ch.postfinance.PostFinanceCheckoutSdk

// After
import ch.postfinance.PostFinanceCheckout
```

### 2. Update initialization

```kotlin
PostFinanceCheckout.init(...)
...
PostFinanceCheckout.instance?.launch(...)
```

---

## Summary

No logic or API changes — only find & replace `PostFinanceCheckoutSdk` → `PostFinanceCheckout` across your codebase.

## Documentation

- [API Reference](./docs/api-reference.md)
- [Integration](./docs/integration.md)
- [Theming](./docs/theming.md)
- [Troubleshooting](./docs/troubleshooting.md)
