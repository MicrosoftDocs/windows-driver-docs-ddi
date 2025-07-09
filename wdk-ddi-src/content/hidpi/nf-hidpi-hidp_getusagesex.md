---
UID: NF:hidpi.HidP_GetUsagesEx
title: HidP_GetUsagesEx function (hidpi.h)
description: The HidP_GetUsagesEx routine returns a list of the all the HID control button usages that are set to ON in a HID report.
old-location: hid\hidp_getusagesex.htm
tech.root: hid
ms.date: 07/09/2025
keywords: ["HidP_GetUsagesEx function"]
ms.keywords: HidP_GetUsagesEx, HidP_GetUsagesEx routine [Human Input Devices], hid.hidp_getusagesex, hidfunc_2a2a6e4a-c966-43d7-8159-115bb6f2376c.xml, hidpi/HidP_GetUsagesEx
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hidparse.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - HidP_GetUsagesEx
 - hidpi/HidP_GetUsagesEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_GetUsagesEx
---

# HidP_GetUsagesEx function

## -description

The **HidP_GetUsagesEx** routine returns a list of the all the HID control button [usages](/windows-hardware/drivers/hid/hid-usages) that are set to ON in a HID report.

## -parameters

### -param ReportType [in]

Specifies a [HIDP_REPORT_TYPE](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type) enumerator value that identifies the report type.

### -param LinkCollection [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) of the button usages. If *LinkCollection* is nonzero, the routine only returns information about the buttons that this link collection contains; otherwise, if *LinkCollection* is zero, the routine returns information about all the buttons in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *PreparsedData*.

### -param ButtonList [in, out]

Pointer to a caller-allocated buffer that routine uses to return the usage and [usage page](/windows-hardware/drivers/hid/hid-usages) identifiers for each button that is set to ON (1).

### -param UsageLength [in, out]

Specifies, on input, the length, in array elements, of the *ButtonList* buffer. Specifies, on output, the number usages that are currently set to ON in the specified report.

### -param PreparsedData [in]

Pointer to a top-level collection's [preparsed data](/windows-hardware/drivers/hid/preparsed-data).

### -param Report [in]

Pointer to a report that contains button data.

### -param ReportLength [in]

Specifies the length, in bytes, of the report located at *Report*.

## -returns

**HidP_GetUsagesEx** returns one of the following status values:

| Return code | Description |
|-------------|-------------|
| **HIDP_STATUS_SUCCESS** | The routine successfully returned all button usages set to ON. |
| **HIDP_STATUS_INVALID_REPORT_LENGTH** | The report length is not valid. |
| **HIDP_STATUS_INVALID_REPORT_TYPE** | The specified report type is not valid. |
| **HIDP_STATUS_BUFFER_TOO_SMALL** | The *UsageList* buffer is too small to hold all the usages currently set to ON in the specified report. |
| **HIDP_STATUS_INCOMPATIBLE_REPORT_ID** | The collection contains buttons in a report of the specified type, but there are no such usages in the specified report. |
| **HIDP_STATUS_INVALID_PREPARSED_DATA** | The preparsed data is not valid. |

## -remarks

User-mode applications and kernel-mode drivers call [HidP_MaxUsageListLength](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_maxusagelistlength) to determine the maximum number of buttons that be returned for specified report type. Alternatively, applications or drivers can call **HidP_GetUsagesEx** and set *(\*UsageLength)* to zero to return the required length in *UsageLength*. In other words, *UsageLength* should be a valid pointer that points to a ULONG value **0** to get the required length.

Applications or drivers determine the required report length from the *Xxx***ReportByteLength** members in a top-level collection's [HIDP_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps) structure.

For more information, see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -see-also

- [HidP_GetButtons](/windows-hardware/drivers/hid/hdpi-h-macros)
- [HidP_GetButtonsEx](/windows-hardware/drivers/hid/hdpi-h-macros)
- [HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps)
- [HidP_GetScaledUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getscaledusagevalue)
- [HidP_GetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue)
- [HidP_GetUsageValueArray](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevaluearray)
- [HidP_GetUsagesEx](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagesex)
- [HidP_MaxUsageListLength](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_maxusagelistlength)
- [USAGE_AND_PAGE](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_usage_and_page)
- [_HIDP_PREPARSED_DATA](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata)
