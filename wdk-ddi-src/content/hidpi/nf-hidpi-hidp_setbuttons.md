---
UID: NF:hidpi.HidP_SetButtons
title: HidP_SetButtons macro
author: windows-driver-content
description: The HidP_SetButtons macro is a mnemonic alias for the HidP_SetUsages function.
tech.root: hid
ms.assetid: 60bba768-dde1-4e31-a30a-fbf977aeb750
ms.author: windowsdriverdev
ms.date: 1/29/2021
ms.topic: macro
ms.keywords: HidP_SetButtons
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
- HidP_SetButtons
product: 
- Windows
targetos: Windows

---

# HidP_SetButtons macro

## -description

The **HidP\_SetButtons** macro is a mnemonic alias for the [**HidP\_SetUsages**](./nf-hidpi-hidp_setusages.md) function.

See [**HidP\_SetUsages**](./nf-hidpi-hidp_setusages.md) for parameter and return details.

## -syntax

```cpp
#define HidP_SetButtons(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle) \
        HidP_SetUsages(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle)
```

## -parameters

## -see-also

[**HidP\_SetUsages**](./nf-hidpi-hidp_setusages.md)