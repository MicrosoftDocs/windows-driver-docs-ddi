---
UID: NF:hidpi.HidP_SetScaledUsageValue
title: HidP_SetScaledUsageValue function (hidpi.h)
description: The HidP_SetScaledUsageValue routine converts a signed and scaled physical number to a HID usage's logical value, and sets the usage value in a specified HID report.
old-location: hid\hidp_setscaledusagevalue.htm
tech.root: hid
ms.date: 01/07/2025
ai-usage: ai-assisted
keywords: ["HidP_SetScaledUsageValue function"]
ms.keywords: HidP_SetScaledUsageValue, HidP_SetScaledUsageValue routine [Human Input Devices], hid.hidp_setscaledusagevalue, hidfunc_0fcd2d78-aae7-4d56-a930-9bf0e4a417bf.xml, hidpi/HidP_SetScaledUsageValue
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
 - HidP_SetScaledUsageValue
 - hidpi/HidP_SetScaledUsageValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_SetScaledUsageValue
---

# HidP_SetScaledUsageValue function

## -description

The **HidP_SetScaledUsageValue** routine converts a signed and scaled physical number to a [HID usage's](/windows-hardware/drivers/hid/hid-usages) logical value, and sets the usage value in a specified HID report.

## -parameters

### -param ReportType [in]

Specifies a **[HIDP_REPORT_TYPE](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type)** enumerator value that indicates the type of HID report located at *Report*.

### -param UsagePage [in]

Specifies the [usage page](/windows-hardware/drivers/hid/hid-usages) of a usage.

### -param LinkCollection [in]

Specifies the [link collection](/windows-hardware/drivers/hid/link-collections) that contains the usage. If *LinkCollection* is nonzero, the routine only sets the usage, if one exists, in this link collection. If *LinkCollection* is zero, the routine sets the first usage it finds in the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) associated with *PreparsedData*.

### -param Usage [in]

Specifies the usage.

### -param UsageValue [in]

Specifies the signed and scaled physical number, which the routine converts to the usage's logical value.

### -param PreparsedData [in]

Pointer to a top-level's [preparsed data](/windows-hardware/drivers/hid/preparsed-data).

### -param Report [in, out]

Pointer to a HID report.

### -param ReportLength [in]

Specifies the size, in bytes, of the HID report located at *Report*, which must be equal to the report length for the specified report type that **[HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps)** returns in a collection's **[HIDP_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps)** structure.

## -returns

**HidP_SetScaledUsageValue** returns one of the following status values:

| Return code | Description |
|--|--|
| **HIDP_STATUS_SUCCESS** | The routine successfully set the usage value. |
| **HIDP_STATUS_BAD_LOG_PHY_VALUES** | The usage has an illegal logical or physical range that prevents scaling. |
| **HIDP_STATUS_VALUE_OUT_OF_RANGE** | The specified physical value is out-of-range and the usage does not have null value. |
| **HIDP_STATUS_INVALID_REPORT_LENGTH** | The report length is not valid. |
| **HIDP_STATUS_INVALID_REPORT_TYPE** | The specified report type is not valid. |
| **HIDP_STATUS_INCOMPATIBLE_REPORT_ID** | The usage does not exist in the specified report, but it does exist in a different report of the specified type. |
| **HIDP_STATUS_INVALID_PREPARSED_DATA** | The preparsed data is not valid. |
| **HIDP_STATUS_USAGE_NOT_FOUND** | The usage does not exist in any report of the specified report type. |
| **HIDP_STATUS_NULL** | The specified physical value is out-of-range, the usage has a null value, and the routine set the null value. |

## -remarks

Scaled values refer to the adjusted output of raw HID data, which are modified based on specific parameters such as sensitivity and the range of the device. This adjustment allows for more meaningful interpretation of the data in relation to the device's intended use.

For further understanding of how HID reports are interpreted and the significance of scaled values, see [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports).

**HidP_SetScaledUsageValue** sets the sign bit.

If the routine returns HIDP_STATUS_INCOMPATIBLE_REPORT_ID, the specified report does contain the usage. However, a user-mode application or kernel-mode driver can set the usage in a zero-initialized report. See [Initializing HID Reports](/windows-hardware/drivers/hid/initializing-hid-reports).

For more information, see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -see-also

- [HID usages](/windows-hardware/drivers/hid/hid-usages)
- [Link collections](/windows-hardware/drivers/hid/link-collections)
- [Top-level collections](/windows-hardware/drivers/hid/top-level-collections)
- [Preparsed data](/windows-hardware/drivers/hid/preparsed-data)
- [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports)
- [Initializing HID Reports](/windows-hardware/drivers/hid/initializing-hid-reports)
- [HID Collections](/windows-hardware/drivers/hid/hid-collections)
- **[HIDP_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps)**
- **[HIDP_REPORT_TYPE](/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type)**
- **[HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps)**
- **[HidP_SetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevalue)**
- **[HidP_SetUsageValueArray](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray)**
- **[_HIDP_PREPARSED_DATA](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata)**
