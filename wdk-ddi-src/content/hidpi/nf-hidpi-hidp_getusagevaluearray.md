---
UID: NF:hidpi.HidP_GetUsageValueArray
title: HidP_GetUsageValueArray function (hidpi.h)
description: The HidP_GetUsageValueArray routine extracts the data associated with a HID control usage value array from a HID report.
old-location: hid\hidp_getusagevaluearray.htm
tech.root: hid
ms.date: 07/09/2025
keywords: ["HidP_GetUsageValueArray function"]
ms.keywords: HidP_GetUsageValueArray, HidP_GetUsageValueArray routine [Human Input Devices], hid.hidp_getusagevaluearray, hidfunc_4e641f34-d016-4b2f-b472-069334d3e461.xml, hidpi/HidP_GetUsageValueArray
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
 - HidP_GetUsageValueArray
 - hidpi/HidP_GetUsageValueArray
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_GetUsageValueArray
---

# HidP_GetUsageValueArray function

## -description

The **HidP_GetUsageValueArray** routine extracts the data associated with a HID control [usage value array](/windows-hardware/drivers/hid/value-capability-arrays) from a HID report.

## -parameters

### -param ReportType [in]

Specifies a [HIDP_REPORT_TYPE](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type) enumerator value that identifies the report type.

### -param UsagePage [in]

Specifies the [usage page](/windows-hardware/drivers/hid/hid-usages) of the usage value array.

### -param LinkCollection [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) that contains the usage value array. If *LinkCollection* is nonzero, the routine only searches for a usage value array in this link collection; otherwise, if *LinkCollection* is zero, the routine searches for a usage value array in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *PreparsedData*.

### -param Usage [in]

Specifies the usage of the usage value array.

### -param UsageValue [in, out]

Pointer to a caller-allocated buffer in which the routine returns the data associated with the usage value array.

### -param UsageValueByteLength [in]

Specifies the length, in bytes, of the buffer at *UsageValue*.

### -param PreparsedData [in]

Pointer to a top-level collection's [preparsed data](/windows-hardware/drivers/hid/preparsed-data).

### -param Report [in]

Pointer to a report that contains values.

### -param ReportLength [in]

Specifies the length, in bytes, of the report located at *Report*.

## -returns

**HidP_GetUsageValueArray** returns one of the following status values:

| Return code | Description |
|-------------|-------------|
| **HIDP_STATUS_SUCCESS** | The routine successfully returned the value's data. |
| **HIDP_STATUS_INVALID_REPORT_LENGTH** | The report length is not valid. |
| **HIDP_INVALID_REPORT_TYPE** | The specified report type is not valid. |
| **HIDP_STATUS_NOT_VALUE_ARRAY** | The requested usage is not a usage value array. |
| **HIDP_STATUS_BUFFER_TOO_SMALL** | The *UsageValue* buffer is too small to hold the requested usage. |
| **HIDP_STATUS_INCOMPATIBLE_REPORT_ID** | The collection contains a usage value array on the specified usage page in a report of the specified type, but there are no such usages in the specified report. |
| **HIDP_STATUS_INVALID_PREPARSED_DATA** | The preparsed data is not valid. |
| **HIDP_STATUS_USAGE_NOT_FOUND** | The collection does not contain a usage value array on the specified usage page in any report of the specified report type. |

## -remarks

The required size, in bytes, of *UsageValueByteLength* is determined by multiplying together the **BitSize** and **ReportCount** members of the usage value array's [HIDP_VALUE_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps) structure, and rounding the result up to the nearest byte.

**HidP_GetUsageValueArray** sets the *UsageValue* buffer in little-endian order, beginning with the least significant bit of the usage's data. The data is not byte-aligned, and is shifted such that the least significant bit of the data is located at the first bit of the *UsageValue* buffer.

**HidP_GetUsageValueArray** is designed to extract all the usage values for a usage whose report count is greater than 1. To extract a usage whose report count is equal to 1, use **HidP_GetUsageValue**.

For more information, see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -see-also

- [HIDP_VALUE_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps)
- [HidP_GetButtons](/windows-hardware/drivers/hid/hdpi-h-macros)
- [HidP_GetButtonsEx](/windows-hardware/drivers/hid/hdpi-h-macros)
- [HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps)
- [HidP_GetScaledUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getscaledusagevalue)
- [HidP_GetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue)
- [HidP_GetUsages](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages)
- [HidP_GetUsagesEx](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagesex)
- [_HIDP_PREPARSED_DATA](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata)
