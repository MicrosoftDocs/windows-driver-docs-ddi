---
UID: NS:hidpi._HIDP_BUTTON_CAPS
title: _HIDP_BUTTON_CAPS (hidpi.h)
description: The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button usage (or a set of buttons associated with a usage range).
old-location: hid\hidp_button_caps.htm
tech.root: hid
ms.assetid: d3d77679-6749-4ef5-a8f2-91639587144a
ms.date: 04/30/2018
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
 - HIDP_BUTTON_CAPS
---

# _HIDP_BUTTON_CAPS structure


## -description

The HIDP_BUTTON_CAPS structure contains information about the capability of a HID control button <a href="/windows-hardware/drivers/hid/hid-usages">usage</a> (or a set of buttons associated with a <a href="/windows-hardware/drivers/hid/hid-usages">usage range</a>).

## -struct-fields

### -field UsagePage

Specifies the <a href="/windows-hardware/drivers/hid/hid-usages">usage page</a> for a usage or usage range.

### -field ReportID

Specifies the report ID of the HID report that contains the usage or usage range.

### -field IsAlias

Indicates, if <b>TRUE</b>, that a button has a set of <a href="/windows-hardware/drivers/hid/hid-usages">aliased usages</a>. Otherwise, if <b>IsAlias</b> is <b>FALSE</b>, the button has only one usage.

### -field BitField

Contains the data fields (one or two bytes) associated with an input, output, or feature main item.

### -field LinkCollection

Specifies the index of the <a href="/windows-hardware/drivers/hid/link-collections">link collection</a> in a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="/windows-hardware/drivers/hid/link-collections">link collection array</a> that contains the usage or usage range. If <b>LinkCollection</b> is zero, the usage or usage range is contained in the top-level collection.

### -field LinkUsage

Specifies the usage of the link collection that contains the usage or usage range. If <b>LinkCollection</b> is zero, <b>LinkUsage</b> specifies the usage of the top-level collection.

### -field LinkUsagePage

Specifies the usage page of the link collection that contains the usage or usage range. If <b>LinkCollection</b> is zero, <b>LinkUsagePage</b> specifies the usage page of the top-level collection.

### -field IsRange

Specifies, if <b>TRUE</b>, that the structure describes a usage range. Otherwise, if <b>IsRange</b> is <b>FALSE</b>, the structure describes a single usage.

### -field IsStringRange

Specifies, if <b>TRUE</b>, that the usage or usage range has a set of string descriptors. Otherwise, if <b>IsStringRange</b> is <b>FALSE</b>, the usage or usage range has zero or one string descriptor.

### -field IsDesignatorRange

Specifies, if <b>TRUE</b>, that the usage or usage range has a set of designators. Otherwise, if <b>IsDesignatorRange</b> is <b>FALSE</b>, the usage or usage range has zero or one designator.

### -field IsAbsolute

Specifies, if <b>TRUE</b>, that the button usage or usage range provides absolute data. Otherwise, if <b>IsAbsolute</b> is <b>FALSE</b>, the button data is the change in state from the previous value.

### -field Reserved

Reserved for internal system use.

### -field Range

Specifies, if <b>IsRange</b> is <b>TRUE</b>, information about a usage range. Otherwise, if <b>IsRange</b> is <b>FALSE</b>, <b>NotRange</b> contains information about a single usage.

### -field Range.UsageMin

Indicates the inclusive lower bound of usage range whose inclusive upper bound is specified by <b>Range.UsageMax</b>.

### -field Range.UsageMax

Indicates the inclusive upper bound of a usage range whose inclusive lower bound is indicated by <b>Range.UsageMin</b>.

### -field Range.StringMin

Indicates the inclusive lower bound of a range of string descriptors (specified by string minimum and string maximum items) whose inclusive upper bound is indicated by <b>Range.StringMax</b>.

### -field Range.StringMax

Indicates the inclusive upper bound of a range of string descriptors (specified by string minimum and string maximum items) whose inclusive lower bound is indicated by <b>Range.StringMin</b>.

### -field Range.DesignatorMin

Indicates the inclusive lower bound of a range of designators (specified by designator minimum and designator maximum items) whose inclusive lower bound is indicated by <b>Range.DesignatorMax</b>.

### -field Range.DesignatorMax

Indicates the inclusive upper bound of a range of designators (specified by designator minimum and designator maximum items) whose inclusive lower bound is indicated by <b>Range.DesignatorMin</b>.

### -field Range.DataIndexMin

Indicates the inclusive lower bound of a sequential range of <a href="/windows-hardware/drivers/hid/data-indices">data indices</a> that correspond, one-to-one and in the same order, to the usages specified by the usage range <b>Range.UsageMin</b> to <b>Range.UsageMax</b>.

### -field Range.DataIndexMax

Indicates the inclusive upper bound of a sequential range of data indices that correspond, one-to-one and in the same order, to the usages specified by the usage range <b>Range.UsageMin</b> to <b>Range.UsageMax</b>.

### -field NotRange

Specifies, if <b>IsRange</b> is <b>FALSE</b>, information about a single usage. Otherwise, if <b>IsRange</b> is <b>TRUE</b>, <b>Range</b> contains information about a usage range.

### -field NotRange.Reserved1

Reserved for internal system use.

### -field NotRange.Usage

Indicates a <a href="/windows-hardware/drivers/hid/hid-usages">usage ID</a>.

### -field NotRange.StringIndex

Indicates a string descriptor ID for the usage specified by <b>NotRange.Usage</b>.

### -field NotRange.Reserved2

Reserved for internal system use.

### -field NotRange.DesignatorIndex

Indicates a designator ID for the usage specified by <b>NotRange.Usage</b>.

### -field NotRange.Reserved3

Reserved for internal system use.

### -field NotRange.DataIndex

Indicates the data index of the usage specified by <b>NotRange.Usage</b>.

### -field NotRange.Reserved4

Reserved for internal system use.

## -remarks

Clients obtain a <a href="/windows-hardware/drivers/hid/button-capability-arrays">button capability array</a> by calling <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps">HidP_GetButtonCaps</a> or <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificbuttoncaps">HidP_GetSpecificButtonCaps</a>. These routines return an array of HIDP_BUTTON_CAPS structures in a caller-allocated buffer. The required buffer length is specified in the <a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure returned by <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>. 

For information about the capabilities of HID control values, see <a href="/windows-hardware/drivers/hid/collection-capability">Collection Capability</a> and <a href="/windows-hardware/drivers/hid/value-capability-arrays">Value Capability Arrays</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps">HidP_GetButtonCaps</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificbuttoncaps">HidP_GetSpecificButtonCaps</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificvaluecaps">HidP_GetSpecificValueCaps</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getvaluecaps">HidP_GetValueCaps</a>