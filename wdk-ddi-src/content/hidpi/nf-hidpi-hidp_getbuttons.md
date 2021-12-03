---
UID: NF:hidpi.HidP_GetButtons
title: HidP_GetButtons macro
author: windows-driver-content
description: The HidP_GetButtons macro is a mnemonic alias for the HHidP_GetUsages function.
tech.root: hid
ms.assetid: 56255105-7dc3-4cc8-9dd0-d0c57339993e
ms.author: windowsdriverdev
ms.date: 12/02/2021
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

The **HidP_GetButtons** macro is a mnemonic alias for the [**HidP_GetUsages**](./nf-hidpi-hidp_getusages.md) function.

## -syntax

```cpp
#define HidP_GetButtons(Rty, UPa, LCo, ULi, ULe, Ppd, Rep, RLe) \
        HidP_GetUsages(Rty, UPa, LCo, ULi, ULe, Ppd, Rep, RLe)
```

## -parameters

### -param Rty [in]

Specifies a [**HIDP_REPORT_TYPE**](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type) enumerator value that identifies the report type.

### -param UPa [in]

Specifies the [usage page](/windows-hardware/drivers/hid/hid-usages) of the button usages. The routine only returns information about buttons on this usage page.

### -param LCo [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) of the button usages. If *LCo* is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if *LCo* is zero, the routine returns information about all the buttons in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *Ppd*.

### -param ULi [out]

Pointer to a caller-allocated buffer that the routine uses to return the usages of all buttons that are set to ON and belong to the usage page specified by *UPa*.

### -param ULe [in, out]

Specifies, on input, the length, in array elements, of the *ULi* buffer. Specifies, on output, the number of buttons that are set to ON on the specified usage page.

### -param Ppd [in]

Pointer to a top-level collection's [pre-parsed data](/windows-hardware/drivers/hid/preparsed-data).

### -param Rep [out]

Pointer to a report.

### -param RLe [in]

Specifies the length, in bytes, of the report located at *Rep*.

## -returns

See [**HidP_GetUsages**](./nf-hidpi-hidp_getusages.md) for return value details.

## -see-also

- [**HidP_GetUsages**](./nf-hidpi-hidp_getusages.md)
