---
UID: NF:hidpi.HidP_SetButtonArray
tech.root: hid
title: HidP_SetButtonArray
ms.date: 11/16/2021
targetos: Windows
description: The HidP_SetButtonArray function sets the state of buttons via an array of HIDP_BUTTON_ARRAY_DATA structures.
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
 - HidP_SetButtonArray
f1_keywords:
 - HidP_SetButtonArray
 - hidpi/HidP_SetButtonArray
dev_langs:
 - c++
---

## -description

The **HidP_SetButtonArray** function sets the state of buttons via an array of [HIDP_BUTTON_ARRAY_DATA](ns-hidpi-hidp_button_array_data.md) structures.

## -parameters

### -param ReportType

A valid value from the [HIDP_REPORT_TYPE](ne-hidpi-_hidp_report_type.md) enum.

### -param UsagePage

The usage page to which the given usage refers.

### -param LinkCollection

(Optional) This value can be used to differentiate between two fields that may have the same *UsagePage* and Usage but exist in different collections. If the value is HIDP_LINK_COLLECTION_UNSPECIFIED, the first found button array matching the *UsagePage* and *Usage* will be returned, regardless of location. If the value is HIDP_LINK_COLLECTION_ROOT, the first found button array, in the root collection, matching the *UsagePage* and *Usage* will be returned.

### -param Usage

The usage whose button array **HidP_SetButtonArray** will set.

### -param ButtonData

The buffer with the values to set into the button array.

### -param ButtonDataLength

Number of elements in the *ButtonData* buffer.

### -param PreparsedData

The parsed data returned from [HIDCLASS](../hidclass/index.md).

### -param Report

The report packet. The first byte *must* be the *ReportId*.

### -param ReportLength

Length of the given report packet in bytes.

## -returns

**HidP_SetButtonArray** returns one of the following status values:

| Return code                         | Description                                                                                                                        |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| HIDP_STATUS_SUCCESS                 | The value array in the report packet was set successfully                                                                          |
| HIDP_STATUS_INVALID_REPORT_TYPE     | *ReportType* is not valid                                                                                                          |
| HIDP_STATUS_INVALID_PREPARSED_DATA  | *PreparsedData* is not valid                                                                                                       |
| HIDP_STATUS_INVALID_REPORT_LENGTH   | The length of the report packet is not equal to the length specified in the **HIDP_CAPS** structure for the given *ReportType*     |
| HIDP_STATUS_REPORT_DOES_NOT_EXIST   | There are no reports on this device for the given *ReportType*                                                                     |
| HIDP_STATUS_NOT_BUTTON_ARRAY        | The control specified is not a button array                                                                                        |
| HIDP_STATUS_INCOMPATIBLE_REPORT_ID  | The specified usage page, usage, and link collection exists in a report with a different report ID than the report being passed in |
| HIDP_STATUS_USAGE_NOT_FOUND         | The usage page, usage, and link collection combination does not exist in any reports for this *ReportType*                         |
| HIDP_STATUS_DATA_INDEX_OUT_OF_RANGE | The *ArrayIndex* for one of the supplied **HIDP_BUTTON_ARRAY_DATA** structures is outside the valid range for this button array    |

## -remarks

A button array occurs when the last usage in the sequence of usages describing a main item, must be repeated because there are less usages defined than the *ReportCount* declared for the given main item. In this case, a single [HIDP_BUTTON_CAPS](ns-hidpi-_hidp_button_caps.md) is allocated for that usage and the *ReportCount* of the **HIDP_BUTTON_CAPS** is set to reflect the number of fields the usage refers.

A **HIDP_BUTTON_CAPS** that describes a button array, will always have *ReportCount* greater than one. If *ReportCount* equals one, then it is not a button array and cannot be used with **HidP_SetButtonArray**. For more information, see [HidP_SetUsages](nf-hidpi-hidp_setusages.md).

**HidP_SetButtonArray** sets the state of buttons for the first button array found, within the specified LinkCollection, with the supplied *Usage* for the supplied *Report*.

## -see-also

- [HidP_GetButtonArray](nf-hidpi-hidp_getbuttonarray.md)
- [HIDP_BUTTON_ARRAY_DATA](ns-hidpi-hidp_button_array_data.md)
- [HIDP_LINK_COLLECTION_NODE](ns-hidpi-_hidp_link_collection_node.md)
- [HIDP_BUTTON_CAPS](ns-hidpi-_hidp_button_caps.md)
- [HidP_SetUsages](nf-hidpi-hidp_setusages.md)
