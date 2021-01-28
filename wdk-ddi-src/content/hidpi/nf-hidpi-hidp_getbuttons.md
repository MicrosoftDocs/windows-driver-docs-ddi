---
UID: NF:hidpi.HidP_GetButtons
title: HidP_GetButtons macro
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: 56255105-7dc3-4cc8-9dd0-d0c57339993e
ms.author: windowsdriverdev
ms.date: 
ms.topic: macro
ms.keywords: HidP_GetButtons
req.header: hidpi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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

## - parameters

## -see-also

[**HidP\_GetUsages**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages)
