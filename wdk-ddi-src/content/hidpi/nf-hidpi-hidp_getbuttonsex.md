---
UID: NF:hidpi.HidP_GetButtonsEx
title: HidP_GetButtonsEx macro
author: windows-driver-content
description: The HidP_GetButtonsEx macro is an mnemonic alias for the HidP_GetUsagesEx function.
tech.root: hid
ms.assetid: 1bb98458-faa7-4d7b-a7d9-d784f0137939
ms.author: windowsdriverdev
ms.date: 12/06/2021
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

The **HidP_GetButtonsEx** macro is a mnemonic alias for the [**HidP_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md) function.

## -syntax

```cpp
#define HidP_GetButtonsEx(Rty, LCo, BLi, ULe, Ppd, Rep, RLe) \
         HidP_GetUsagesEx(Rty, LCo, BLi, ULe, Ppd, Rep, RLe)
```

## -parameters

### -param Rty [in]

Specifies a [**HIDP_REPORT_TYPE**](./ne-hidpi-_hidp_report_type.md) enumerator value that identifies the report type.

### -param LCo [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) of the button usages. If *LCo* is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if *LCo* is zero, the routine returns information about all the buttons in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *Ppd*.

### -param BLi [in, out]

Pointer to a caller-allocated buffer that routine uses to return the usage and [usage page](/windows-hardware/drivers/hid/hid-usages) identifiers for each button that is set to ON (1).

### -param ULe [in, out]

Specifies, on input, the length, in array elements, of the *BLi* buffer. Specifies, on output, the number usages that are currently set to ON in the specified report.

### -param Ppd [in]

Pointer to a top-level collection's [pre-parsed data](/windows-hardware/drivers/hid/preparsed-data).

### -param Rep [in]

Pointer to a report that contains button data.

### -param RLe [in]

Specifies the length, in bytes, of the report located at *Rep*.

## -remarks

See [**HidP_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md) for return value details.

## -see-also

- [**HidP_GetUsagesEx**](./nf-hidpi-hidp_getusagesex.md)