---
UID: NS:hidpi._HIDP_BUTTON_CAPS
title: _HIDP_BUTTON_CAPS (hidpi.h)
description: The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button usage (or a set of buttons associated with a usage range).
old-location: hid\hidp_button_caps.htm
tech.root: hid
ms.date: 11/11/2021
keywords: ["HIDP_BUTTON_CAPS structure"]
ms.keywords: "*PHIDP_BUTTON_CAPS, HIDP_BUTTON_CAPS, HIDP_BUTTON_CAPS structure [Human Input Devices], PHIDP_BUTTON_CAPS, PHIDP_BUTTON_CAPS structure pointer [Human Input Devices], _HIDP_BUTTON_CAPS, hid.hidp_button_caps, hidpi/HIDP_BUTTON_CAPS, hidpi/PHIDP_BUTTON_CAPS, hidstrct_0fa7f0ef-afc7-482a-bcf0-c8c78c3d18f7.xml"
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: HIDP_BUTTON_CAPS, *PHIDP_BUTTON_CAPS
f1_keywords:
 - _HIDP_BUTTON_CAPS
 - hidpi/_HIDP_BUTTON_CAPS
 - PHIDP_BUTTON_CAPS
 - hidpi/PHIDP_BUTTON_CAPS
 - HIDP_BUTTON_CAPS
 - hidpi/HIDP_BUTTON_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - _HIDP_BUTTON_CAPS
 - PHIDP_BUTTON_CAPS
 - HIDP_BUTTON_CAPS
---

# _HIDP_BUTTON_CAPS structure

## -description

The **HIDP_BUTTON_CAPS** structure contains information about the capability of a HID control button [usage](/windows-hardware/drivers/hid/hid-usages) (or a set of buttons associated with a [usage range](/windows-hardware/drivers/hid/hid-usages)).

## -struct-fields

### -field UsagePage

Specifies the [usage page](/windows-hardware/drivers/hid/hid-usages) for a usage or usage range.

### -field ReportID

Specifies the report ID of the HID report that contains the usage or usage range.

### -field IsAlias

Indicates, if **TRUE**, that a button has a set of [aliased usages](/windows-hardware/drivers/hid/hid-usages). Otherwise, if **IsAlias** is **FALSE**, the button has only one usage.

### -field BitField

Contains the data fields (one or two bytes) associated with an input, output, or feature main item.

### -field LinkCollection

Specifies the index of the [link collection](/windows-hardware/drivers/hid/link-collections) in a [top-level collection's](/windows-hardware/drivers/hid/top-level-collections) [link collection array](/windows-hardware/drivers/hid/link-collections) that contains the usage or usage range. If **LinkCollection** is zero, the usage or usage range is contained in the top-level collection.

### -field LinkUsage

Specifies the usage of the link collection that contains the usage or usage range. If **LinkCollection** is zero, **LinkUsage** specifies the usage of the top-level collection.

### -field LinkUsagePage

Specifies the usage page of the link collection that contains the usage or usage range. If **LinkCollection** is zero, **LinkUsagePage** specifies the usage page of the top-level collection.

### -field IsRange

Specifies, if **TRUE**, that the structure describes a usage range. Otherwise, if **IsRange** is **FALSE**, the structure describes a single usage.

### -field IsStringRange

Specifies, if **TRUE**, that the usage or usage range has a set of string descriptors. Otherwise, if **IsStringRange** is **FALSE**, the usage or usage range has zero or one string descriptor.

### -field IsDesignatorRange

Specifies, if **TRUE**, that the usage or usage range has a set of designators. Otherwise, if **IsDesignatorRange** is **FALSE**, the usage or usage range has zero or one designator.

### -field IsAbsolute

Specifies, if **TRUE**, that the button usage or usage range provides absolute data. Otherwise, if **IsAbsolute** is **FALSE**, the button data is the change in state from the previous value.

### -field ReportCount

HID defined report count. Available starting with API version 2.0.

### -field Reserved2

Reserved for internal system use.

### -field Reserved

Reserved for internal system use.

### -field Range

Specifies, if **IsRange** is **TRUE**, information about a usage range. Otherwise, if **IsRange** is **FALSE**, **NotRange** contains information about a single usage.

### -field Range.UsageMin

Indicates the inclusive lower bound of usage range whose inclusive upper bound is specified by **Range.UsageMax**.

### -field Range.UsageMax

Indicates the inclusive upper bound of a usage range whose inclusive lower bound is indicated by **Range.UsageMin**.

### -field Range.StringMin

Indicates the inclusive lower bound of a range of string descriptors (specified by string minimum and string maximum items) whose inclusive upper bound is indicated by **Range.StringMax**.

### -field Range.StringMax

Indicates the inclusive upper bound of a range of string descriptors (specified by string minimum and string maximum items) whose inclusive lower bound is indicated by **Range.StringMin**.

### -field Range.DesignatorMin

Indicates the inclusive lower bound of a range of designators (specified by designator minimum and designator maximum items) whose inclusive lower bound is indicated by **Range.DesignatorMax**.

### -field Range.DesignatorMax

Indicates the inclusive upper bound of a range of designators (specified by designator minimum and designator maximum items) whose inclusive lower bound is indicated by **Range.DesignatorMin**.

### -field Range.DataIndexMin

Indicates the inclusive lower bound of a sequential range of [data indices](/windows-hardware/drivers/hid/data-indices) that correspond, one-to-one and in the same order, to the usages specified by the usage range **Range.UsageMin** to **Range.UsageMax**.

### -field Range.DataIndexMax

Indicates the inclusive upper bound of a sequential range of data indices that correspond, one-to-one and in the same order, to the usages specified by the usage range **Range.UsageMin** to **Range.UsageMax**.

### -field NotRange

Specifies, if **IsRange** is **FALSE**, information about a single usage. Otherwise, if **IsRange** is **TRUE**, **Range** contains information about a usage range.

### -field NotRange.Reserved1

Reserved for internal system use.

### -field NotRange.Usage

Indicates a [usage ID](/windows-hardware/drivers/hid/hid-usages).

### -field NotRange.StringIndex

Indicates a string descriptor ID for the usage specified by **NotRange.Usage**.

### -field NotRange.Reserved2

Reserved for internal system use.

### -field NotRange.DesignatorIndex

Indicates a designator ID for the usage specified by **NotRange.Usage**.

### -field NotRange.Reserved3

Reserved for internal system use.

### -field NotRange.DataIndex

Indicates the data index of the usage specified by **NotRange.Usage**.

### -field NotRange.Reserved4

Reserved for internal system use.

## -remarks

Clients obtain a [button capability array](/windows-hardware/drivers/hid/button-capability-arrays) by calling [HidP_GetButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps) or [HidP_GetSpecificButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificbuttoncaps). These routines return an array of HIDP_BUTTON_CAPS structures in a caller-allocated buffer. The required buffer length is specified in the [HIDP_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps) structure returned by [HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps).

For information about the capabilities of HID control values, see [Collection Capability](/windows-hardware/drivers/hid/collection-capability) and [Value Capability Arrays](/windows-hardware/drivers/hid/value-capability-arrays).

When a report descriptor declares an input, output, or feature main item with fewer usage declarations than the *ReportCount*, then the last usage applies to all remaining unspecified count in that main item. As an example, you might have data that required many fields to describe, possibly buffered bytes. In this case, only one value cap structure is allocated for these associated fields, all with the same usage, and *ReportCount* reflects the number of fields involved. Normally *ReportCount* is one. To access all of the fields in such a value structure would require using [HidP_GetUsageValueArray](nf-hidpi-hidp_getusagevaluearray.md) and [HidP_SetUsageValueArray](nf-hidpi-hidp_setusagevaluearray.md). The [HidP_GetUsageValue](nf-hidpi-hidp_getusagevalue.md) and [HidP_SetScaledUsageValue](nf-hidpi-hidp_setscaledusagevalue.md) functions will also work. However, these functions only work with the first field of the structure.

## -see-also

- [HIDP_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps)
- [HIDP_VALUE_CAPS](/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps)
- [HidP_GetButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps)
- [HidP_GetCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps)
- [HidP_GetSpecificButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificbuttoncaps)
- [HidP_GetSpecificValueCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificvaluecaps)
- [HidP_GetValueCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getvaluecaps)
