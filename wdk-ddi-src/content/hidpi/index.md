---
UID: NA:hidpi
ms.assetid: 755e703a-2165-39e7-a3dc-27fc70f42714
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Hidpi.h header



This header is used by Human Interface Devices (HID). For more information, see
- [Human Interface Devices (HID)](../_hid/index.md)

Hidpi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [HidP_GetButtonCaps function](nf-hidpi-hidp_getbuttoncaps.md) | The HidP_GetButtonCaps routine returns a button capability array that describes all the HID control buttons in a top-level collection for a specified type of HID report. |
| [HidP_GetCaps function](nf-hidpi-hidp_getcaps.md) | The HidP_GetCaps routine returns a top-level collection's HIDP_CAPS structure. |
| [HidP_GetData function](nf-hidpi-hidp_getdata.md) | The HidP_GetData routine returns, for a specified report, an array of HIDP_DATA structures that identify the data indices of all HID control buttons that are currently set to ON (1), and the data indices and data associated with all HID control values. |
| [HidP_GetExtendedAttributes function](nf-hidpi-hidp_getextendedattributes.md) | The HidP_GetExtendedAttributes routine returns the extended attributes of a HID control. |
| [HidP_GetLinkCollectionNodes function](nf-hidpi-hidp_getlinkcollectionnodes.md) | The HidP_GetLinkCollectionNodes routine returns a top-level collection's link collection array. |
| [HidP_GetScaledUsageValue function](nf-hidpi-hidp_getscaledusagevalue.md) | The HidP_GetScaledUsageValue routine returns the signed and scaled result of a HID control value extracted from a HID report. |
| [HidP_GetSpecificButtonCaps function](nf-hidpi-hidp_getspecificbuttoncaps.md) | The HidP_GetSpecificButtonCaps routine returns a button capability array that describes all HID control buttons in a top-level collection that meet a specified selection criteria. |
| [HidP_GetSpecificValueCaps function](nf-hidpi-hidp_getspecificvaluecaps.md) | The HidP_GetSpecificValueCaps routine returns a value capability array that describes all HID control values that meet a specified selection criteria. |
| [HidP_GetUsageValue function](nf-hidpi-hidp_getusagevalue.md) | The HidP_GetUsageValue routine extracts the data associated with a HID control value that matches the selection criteria in a HID report. |
| [HidP_GetUsageValueArray function](nf-hidpi-hidp_getusagevaluearray.md) | The HidP_GetUsageValueArray routine extracts the data associated with a HID control usage value array from a HID report. |
| [HidP_GetUsages function](nf-hidpi-hidp_getusages.md) | The HidP_GetUsages routine returns a list of all the HID control button usages that are on a specified usage page and are set to ON in a HID report. |
| [HidP_GetUsagesEx function](nf-hidpi-hidp_getusagesex.md) | The HidP_GetUsagesEx routine returns a list of the all the HID control button usages that are set to ON in a HID report. |
| [HidP_GetValueCaps function](nf-hidpi-hidp_getvaluecaps.md) | The HidP_GetValueCaps routine returns a value capability array that describes all the HID control values in a top-level collection for a specified type of HID report. |
| [HidP_InitializeReportForID function](nf-hidpi-hidp_initializereportforid.md) | The HidP_InitializeReportForID routine initializes a HID report. |
| [HidP_MaxDataListLength function](nf-hidpi-hidp_maxdatalistlength.md) | The HidP_MaxDataListLength routine returns the maximum number of HIDP_DATA structures that HidP_GetData can return for a specified type of HID report and a specified top-level collection. |
| [HidP_MaxUsageListLength function](nf-hidpi-hidp_maxusagelistlength.md) | The HidP_MaxUsageListLength routine returns the maximum number of HID usages that HidP_GetUsages can return for a specified type of HID report and a specified top-level collection. |
| [HidP_SetData function](nf-hidpi-hidp_setdata.md) | The HidP_SetData routine sets a specified set of HID control button and value usages in a HID report. |
| [HidP_SetScaledUsageValue function](nf-hidpi-hidp_setscaledusagevalue.md) | The HidP_SetScaledUsageValue routine converts a signed and scaled physical number to a HID usage's logical value, and sets the usage value in a specified HID report. |
| [HidP_SetUsageValue function](nf-hidpi-hidp_setusagevalue.md) | The HidP_SetUsageValue routine sets a HID control value in a specified HID report. |
| [HidP_SetUsageValueArray function](nf-hidpi-hidp_setusagevaluearray.md) | The HidP_SetUsageValueArray routine sets a HID control usage value array in a specified HID report. |
| [HidP_SetUsages function](nf-hidpi-hidp_setusages.md) | The HidP_SetUsages routine sets specified HID control buttons ON (1) in a HID report. |
| [HidP_TranslateUsagesToI8042ScanCodes function](nf-hidpi-hidp_translateusagestoi8042scancodes.md) | The HidP_TranslateUsagesToI8042ScanCodes routine maps a list of HID usages on the HID_USAGE_PAGE_KEYBOARD usage page to their respective PS/2 scan codes (Scan Code Set 1). |
| [HidP_UnsetUsages function](nf-hidpi-hidp_unsetusages.md) | The HidP_UnsetUsages routine sets specified HID control button usages OFF (zero) in a HID report. |
| [HidP_UsageAndPageListDifference function](nf-hidpi-hidp_usageandpagelistdifference.md) | The HidP_UsageAndPageListDifference routine is not implemented. |
| [HidP_UsageListDifference function](nf-hidpi-hidp_usagelistdifference.md) | The HidP_UsageListDifference routine returns the differences between two arrays of HID usages. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_HIDP_BUTTON_CAPS structure](ns-hidpi-_hidp_button_caps.md) | The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button usage (or a set of buttons associated with a usage range). |
| [_HIDP_CAPS structure](ns-hidpi-_hidp_caps.md) | The HIDP_CAPS structure contains information about a top-level collection's capability. |
| [_HIDP_DATA structure](ns-hidpi-_hidp_data.md) | The HIDP_DATA structure contains information about a HID control's data index and value in a HID report. |
| [_HIDP_EXTENDED_ATTRIBUTES structure](ns-hidpi-_hidp_extended_attributes.md) | The HIDP_EXTENDED_ATTRIBUTES structure contains information about the global items specified for a HID control that the HID parser did not recognize. |
| [_HIDP_LINK_COLLECTION_NODE structure](ns-hidpi-_hidp_link_collection_node.md) | The HIDP_LINK_COLLECTION_NODE structure contains information about a link collection in a top-level collection's link collection array. |
| [_HIDP_UNKNOWN_TOKEN structure](ns-hidpi-_hidp_unknown_token.md) | The HIDP_UNKNOWN_TOKEN structure contains information about a global item that the HID parser did not recognize. |
| [_HIDP_VALUE_CAPS structure](ns-hidpi-_hidp_value_caps.md) | The HIDP_VALUE_CAPS structure contains information that describes the capability of a set of HID control values (either a single usage or a usage range). |
| [_USAGE_AND_PAGE structure](ns-hidpi-_usage_and_page.md) | The USAGE_AND_PAGE structure specifies the usage page and usage ID of a HID control. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_HIDP_REPORT_TYPE enumeration](ne-hidpi-_hidp_report_type.md) | The HIDP_REPORT_TYPE enumeration type is used to specify a HID report type. |
