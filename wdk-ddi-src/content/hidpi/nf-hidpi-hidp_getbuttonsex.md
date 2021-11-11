---
UID: NF:hidpi.HidP_GetButtonsEx
title: HidP_GetButtonsEx macro
author: windows-driver-content
description: The HidP_GetButtonsEx macro is an mnemonic alias for the HidP_GetUsagesEx function.
tech.root:
ms.assetid: 1bb98458-faa7-4d7b-a7d9-d784f0137939
ms.author: windowsdriverdev
ms.date: 1/29/2021
ms.keywords: HidP_GetButtonsEx
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
- HidP_GetButtonsEx
product: 
- Windows
targetos: Windows

---

# HidP_GetButtonsEx macro

## -description

The **HidP\_GetButtonsEx** macro is an mnemonic alias for the [**HidP\_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md) function.

See [**HidP\_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md) for parameter and return details.

## -syntax

```cpp
#define HidP_GetButtonsEx(Rty, LCo, BLi, ULe, Ppd, Rep, RLe)  \
         HidP_GetUsagesEx(Rty, LCo, BLi, ULe, Ppd, Rep, RLe)
```

## -see-also

[**HidP\_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md)