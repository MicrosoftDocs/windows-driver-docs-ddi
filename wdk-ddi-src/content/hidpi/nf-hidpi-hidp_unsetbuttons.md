---
UID: NF:hidpi.HidP_UnsetButtons
title: HidP_UnsetButtons macro
author: windows-driver-content
description: TBD
tech.root: hid
ms.assetid: 72aef86d-8403-451d-8a19-6050d56646c6
ms.author: windowsdriverdev
ms.date: 1/29/2021
ms.topic: macro
ms.keywords: HidP_UnsetButtons
req.header: hidpi.h
req.include-header: hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- hidpi.h
api_name: 
- HidP_UnsetButtons
product: 
- Windows
targetos: Windows

---

# HidP_UnsetButtons macro

## -description

The **HidP\_UnsetButtons** macro is a mnemonic alias for the [**HidP\_UnsetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_unsetusages) function.

See [**HidP\_UnsetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_unsetusages) for parameter and return details.

## -syntax

```cpp
#define HidP_UnsetButtons(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle) \
        HidP_UnsetUsages(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle)
```

## -parameters

## -see-also

[**HidP\_UnsetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_unsetusages)
