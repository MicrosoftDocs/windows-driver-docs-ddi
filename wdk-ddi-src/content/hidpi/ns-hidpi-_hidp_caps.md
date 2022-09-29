---
UID: NS:hidpi._HIDP_CAPS
title: _HIDP_CAPS (hidpi.h)
description: The HIDP_CAPS structure contains information about a top-level collection's capability.
old-location: hid\hidp_caps.htm
tech.root: hid
ms.date: 04/28/2022
keywords: ["HIDP_CAPS structure"]
ms.keywords: "*PHIDP_CAPS, HIDP_CAPS, HIDP_CAPS structure [Human Input Devices], PHIDP_CAPS, PHIDP_CAPS structure pointer [Human Input Devices], _HIDP_CAPS, hid.hidp_caps, hidpi/HIDP_CAPS, hidpi/PHIDP_CAPS, hidstrct_2ef93e42-2fd2-4dff-87fb-11f1d1342b07.xml"
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
req.typenames: HIDP_CAPS, *PHIDP_CAPS
f1_keywords:
 - _HIDP_CAPS
 - hidpi/_HIDP_CAPS
 - PHIDP_CAPS
 - hidpi/PHIDP_CAPS
 - HIDP_CAPS
 - hidpi/HIDP_CAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidpi.h
api_name:
 - _HIDP_CAPS
 - PHIDP_CAPS
 - HIDP_CAPS
---

# _HIDP_CAPS structure

## -description

The HIDP_CAPS structure contains information about a top-level [collection's capability](/windows-hardware/drivers/hid/collection-capability).

## -struct-fields

### -field Usage

Specifies a [top-level collection's](/windows-hardware/drivers/hid/top-level-collections) [usage ID](/windows-hardware/drivers/hid/hid-usages).

### -field UsagePage

Specifies the top-level collection's [usage page](/windows-hardware/drivers/hid/hid-usages).

### -field InputReportByteLength

Specifies the maximum size, in bytes, of all the input reports. Includes the report ID, which is prepended to the report data. If report ID is not used, the ID value is zero.

### -field OutputReportByteLength

Specifies the maximum size, in bytes, of all the output reports. Includes the report ID, which is prepended to the report data. If report ID is not used, the ID value is zero.

### -field FeatureReportByteLength

Specifies the maximum length, in bytes, of all the feature reports. Includes the report ID, which is prepended to the report data. If report ID is not used, the ID value is zero.

### -field Reserved

Reserved for internal system use.

### -field NumberLinkCollectionNodes

Specifies the number of [HIDP_LINK_COLLECTION_NODE](./ns-hidpi-_hidp_link_collection_node.md) structures that are returned for this top-level collection by [HidP_GetLinkCollectionNodes](./nf-hidpi-hidp_getlinkcollectionnodes.md).

### -field NumberInputButtonCaps

Specifies the number of input [HIDP_BUTTON_CAPS](./ns-hidpi-_hidp_button_caps.md) structures that [HidP_GetButtonCaps](./nf-hidpi-hidp_getbuttoncaps.md) returns.

### -field NumberInputValueCaps

Specifies the number of input [HIDP_VALUE_CAPS](./ns-hidpi-_hidp_value_caps.md) structures that [HidP_GetValueCaps](./nf-hidpi-hidp_getvaluecaps.md) returns.

### -field NumberInputDataIndices

Specifies the number of [data indices](/windows-hardware/drivers/hid/data-indices) assigned to buttons and values in all input reports.

### -field NumberOutputButtonCaps

Specifies the number of output HIDP_BUTTON_CAPS structures that **HidP_GetButtonCaps** returns.

### -field NumberOutputValueCaps

Specifies the number of output HIDP_VALUE_CAPS structures that **HidP_GetValueCaps** returns.

### -field NumberOutputDataIndices

Specifies the number of data indices assigned to buttons and values in all output reports.

### -field NumberFeatureButtonCaps

Specifies the total number of feature HIDP_BUTTONS_CAPS structures that **HidP_GetButtonCaps** returns.

### -field NumberFeatureValueCaps

Specifies the total number of feature HIDP_VALUE_CAPS structures that **HidP_GetValueCaps** returns.

### -field NumberFeatureDataIndices

Specifies the number of data indices assigned to buttons and values in all feature reports.

## -remarks

Callers of the [HIDClass support routines](../index.yml) use the information provided in this structure when a called routine requires, as input, the size of a report type, the number of link collection nodes, the number of control capabilities, or the number of data indices.

## -see-also

- [HIDP_BUTTON_CAPS](./ns-hidpi-_hidp_button_caps.md)
- [HIDP_LINK_COLLECTION_NODE](./ns-hidpi-_hidp_link_collection_node.md)
- [HIDP_VALUE_CAPS](./ns-hidpi-_hidp_value_caps.md)
- [HidP_GetButtonCaps](./nf-hidpi-hidp_getbuttoncaps.md)
- [HidP_GetCaps](./nf-hidpi-hidp_getcaps.md)
- [HidP_GetLinkCollectionNodes](./nf-hidpi-hidp_getlinkcollectionnodes.md)
- [HidP_GetSpecificButtonCaps](./nf-hidpi-hidp_getspecificbuttoncaps.md)
- [HidP_GetSpecificValueCaps](./nf-hidpi-hidp_getspecificvaluecaps.md)
- [HidP_GetValueCaps](./nf-hidpi-hidp_getvaluecaps.md)