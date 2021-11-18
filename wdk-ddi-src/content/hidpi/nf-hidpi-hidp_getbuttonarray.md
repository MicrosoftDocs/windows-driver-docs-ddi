---
UID: NF:hidpi.HidP_GetButtonArray
tech.root: hid
title: HidP_GetButtonArray
ms.date: 11/17/2021
targetos: Windows
description: HidP_GetButtonArray returns an array of HIDP_BUTTON_ARRAY_DATA structures, one for each button that is set to ON, for the specified report.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidpi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidpi.h
api_name:
 - HidP_GetButtonArray
f1_keywords:
 - HidP_GetButtonArray
 - hidpi/HidP_GetButtonArray
dev_langs:
 - c++
---

## -description

**HidP_GetButtonArray** returns an array of [HIDP_BUTTON_ARRAY_DATA](ns-hidpi-hidp_button_array_data.md) structures, one for each button that is set to `ON`, for the specified report.

## -parameters

### -param ReportType

A value from the [HIDP_REPORT_TYPE](ne-hidpi-_hidp_report_type.md) enum.

### -param UsagePage

The usage page to which the given usage refers.

### -param LinkCollection

(Optional) This value can be used to differentiate between two fields that may have the same *UsagePage* and *Usage* but exist in different collections. If the *LinkCollection* value is **HIDP_LINK_COLLECTION_UNSPECIFIED**, the first button array found matching the *UsagePage* and *Usage* will be returned, regardless of location. If the *LinkCollection* value is **HIDP_LINK_COLLECTION_ROOT**, the first button array found in the root collection matching the *UsagePage* and *Usage* will be returned.

### -param Usage

The usage whose buttons **HidP_GetButtonArray** will retrieve.

### -param ButtonData

An array of **HIDP_BUTTON_ARRAY_DATA** structures where the data of buttons set to `ON` will be placed. The number of elements required is the *ReportCount* field of the [HIDP_BUTTON_CAPS](ns-hidpi-_hidp_button_caps.md) for this control. This buffer is provided by the caller.

### -param ButtonDataLength

As input, this parameter specifies the length of the *ButtonData* parameter in number of array elements, not number of bytes. As output, if HIDP_STATUS_SUCCESS is returned, this value is set to indicate how many of those array elements were filled in by the function. The maximum number of **HIDP_BUTTON_ARRAY_DATA** structures that can be returned is determined by HIDP_BUTTON_CAPS.ReportCount. If HIDP_STATUS_BUFFER_TOO_SMALL is returned, this value contains the number of array elements needed to successfully complete the request.

### -param PreparsedData

The preparsed data returned by the [HIDCLASS](../hidclass/index.md).

### -param Report

The report packet. (Note: The first byte MUST be the ReportId; this will be correctly set if the report is read from the system)

### -param ReportLength

Length of the given report packet (in bytes).

## -returns

**HidP_GetButtonArray** returns one of the following status values:

| Return code                        | Description                                                                                                                       |
|------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| HIDP_STATUS_SUCCESS                | Successfully retrieved the buttons from the report packet                                                                         |
| HIDP_STATUS_INVALID_REPORT_TYPE    | The *ReportType* parameter is not valid                                                                                           |
| HIDP_STATUS_INVALID_PREPARSED_DATA | The *PreparsedData* parameter is not valid                                                                                        |
| HIDP_STATUS_INVALID_REPORT_LENGTH  | The length of the report packet is not equal to the length specified in the **HIDP_CAPS** structure for the given *ReportType*    |
| HIDP_STATUS_NOT_BUTTON_ARRAY       | The control specified is not a button array                                                                                       |
| HIDP_STATUS_BUFFER_TOO_SMALL       | The size of the passed in buffer in which to return the array is too small                                                        |
| HIDP_STATUS_INCOMPATIBLE_REPORT_ID | The specified usage page, usage and link collection exists in a report with a different report ID than the report being passed in |
| HIDP_STATUS_USAGE_NOT_FOUND        | The usage page, usage, and link collection combination does not exist in any reports for this *ReportType*                        |

## -remarks

The caller should use [HidP_GetVersion](nf-hidpi-hidp_getversion.md) to determine if this function is available. **HidP_GetButtonArray** is only available if **HidP_GetVersion** returns a value >= 2.

A button array occurs when the last usage in the sequence of usages describing a main item, must be repeated because there are less usages defined than the *ReportCount* declared for the given main item. In this case, a single **HIDP_BUTTON_CAPS** is allocated for that usage and the *ReportCount* of the **HIDP_BUTTON_CAPS** is set to reflect the number of fields to which the usage refers.

A **HIDP_BUTTON_CAPS** that describes a button array will always have *ReportCount* greater than one. If *ReportCount* equals one, then it is not a button array and cannot be used with **HidP_GetButtonArray**. See [HidP_GetUsages](nf-hidpi-hidp_getusages.md) instead.

## -see-also

- [HidP_GetVersion](nf-hidpi-hidp_getversion.md)
- [HIDP_BUTTON_ARRAY_DATA](ns-hidpi-hidp_button_array_data.md)
- [HIDP_REPORT_TYPE](ne-hidpi-_hidp_report_type.md)
- [HIDP_BUTTON_CAPS](ns-hidpi-_hidp_button_caps.md)
- [HidP_GetUsages](nf-hidpi-hidp_getusages.md)
- [HidP_SetButtonArray](nf-hidpi-hidp_setbuttonarray.md)
