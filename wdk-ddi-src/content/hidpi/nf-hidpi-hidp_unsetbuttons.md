---
UID: NF:hidpi.HidP_UnsetButtons
title: HidP_UnsetButtons macro
author: windows-driver-content
description: The HidP_UnsetButtons macro is a mnemonic alias for the HidP_UnsetUsages function.
tech.root: hid
ms.assetid: 72aef86d-8403-451d-8a19-6050d56646c6
ms.author: windowsdriverdev
ms.date: 12/06/2021
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

The **HidP_UnsetButtons** macro is a mnemonic alias for the [**HidP_UnsetUsages**](./nf-hidpi-hidp_unsetusages.md) function.

## -syntax

```cpp
#define HidP_UnsetButtons(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle) \
        HidP_UnsetUsages(Rty, Up, Lco, ULi, ULe, Ppd, Rep, Rle)
```

## -parameters

### -param Rty [in]

Specifies a [**HIDP_REPORT_TYPE**](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type) enumerator value that indicates the type of report located at *Rep*.

### -param Up [in]

Specifies the usage page of the usages specified by *ULi*.

### -param Lco [in, optional]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) that contains the usages. If *Lco* is nonzero, the routine only sets the usages, if they exist, in this link collection. If *Lco* is zero, the routine sets the first usage for each usage it finds in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *Ppd*.

### -param ULi [in, out]

Pointer to the array of usages to set to OFF.

### -param ULe [in, out]

Specifies, on input, the number of usages in *ULi*. See the Remarks section for information about the output value.

### -param Ppd [in]

Pointer to the [pre-parsed data](/windows-hardware/drivers/hid/preparsed-data) of the top-level collection associated with the report located at *Rep*.

### -param Rep [in]

Pointer to a report.

### -param Rle [in]

Specifies the size, in bytes, of the report located at *Rep*, which must be equal to the report length for the specified report type that [**HidP_GetCaps**](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps) returns in a collection's [**HIDP_CAPS**](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps) structure.

## -remarks

See [**HidP_UnsetUsages**](./nf-hidpi-hidp_unsetusages.md) for return value details.

## -see-also

- [**HidP_UnsetUsages**](./nf-hidpi-hidp_unsetusages.md)
