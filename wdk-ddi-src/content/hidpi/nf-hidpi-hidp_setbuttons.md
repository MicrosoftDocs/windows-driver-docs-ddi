---
UID: NF:hidpi.HidP_SetButtons
title: HidP_SetButtons macro
author: windows-driver-content
description: The HidP_SetButtons macro is a mnemonic alias for the HidP_SetUsages function.
tech.root: hid
ms.assetid: 60bba768-dde1-4e31-a30a-fbf977aeb750
ms.author: windowsdriverdev
ms.date: 12/06/2021
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
targetos: Windows
---

# HidP_SetButtons macro

## -description

The **HidP_SetButtons** macro is a mnemonic alias for the [**HidP_SetUsages**](./nf-hidpi-hidp_setusages.md) function.

## -syntax

```cpp
#define HidP_SetButtons(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle) \
        HidP_SetUsages(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle)
```

## -parameters

### -param Rty [in]

Specifies a [**HIDP_REPORT_TYPE**](./ne-hidpi-_hidp_report_type.md) enumerator value that indicates the type of report located at *Rep*.

### -param Up [in]

Specifies the [usage page](/windows-hardware/drivers/hid/hid-usages) for the usages specified by *ULi*.

### -param Lco [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) that contains the usages. If *Lco* is nonzero, the routine only sets the usages, if they exist, in this link collection. If *Lco* is zero, the routine sets the first usage for each specified usage in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *Ppd*.

### -param ULi [in, out]

Pointer to the array of usages.

### -param ULe [in, out]

Specifies, on input, the number of usages in *ULi*. See the Remarks section for information about the output value.

### -param Ppd [in]

Pointer to the [pre-parsed data](/windows-hardware/drivers/hid/preparsed-data) of the top-level collection associated with the report located at *Rep*.

### -param Rep [in]

Pointer to a report.

### -param Rle [in]

Specifies the size, in bytes, of the report located at *Rep*, which must be equal to the report length for the specified report type that [**HidP_GetCaps**](./nf-hidpi-hidp_getcaps.md) returns in a collection's [**HIDP_CAPS**](./ns-hidpi-_hidp_caps.md) structure.

## -remarks

See [**HidP_SetUsages**](./nf-hidpi-hidp_setusages.md) for return value details.

## -see-also

- [**HidP_SetUsages**](./nf-hidpi-hidp_setusages.md)