---
UID: NF:hidpi.HidP_GetButtons
title: HidP_GetButtons macro
author: windows-driver-content
description: HidP_GetButtons is a mnemonic alias for HHidP_GetUsages
tech.root: hid
ms.assetid: 56255105-7dc3-4cc8-9dd0-d0c57339993e
ms.author: windowsdriverdev
ms.date: 1/29/2021
ms.topic: macro
ms.keywords: HidP_GetButtons
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
- HidP_GetButtons
product: 
- Windows
targetos: Windows

---

# HidP_GetButtons macro

## -description

The **HidP\_GetButtons** macro is a mnemonic alias for the [**HidP\_GetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages) routine.

## -syntax

```cpp
#define HidP_GetButtons(Rty, UPa, LCo, ULi, ULe, Ppd, Rep, RLe) \
        HidP_GetUsages(Rty, UPa, LCo, ULi, ULe, Ppd, Rep, RLe)
```

## -parameters

## -returns

## -remarks

See [**HidP\_GetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages) for parameter and return specifics.

## -see-also

[**HidP\_GetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages)
