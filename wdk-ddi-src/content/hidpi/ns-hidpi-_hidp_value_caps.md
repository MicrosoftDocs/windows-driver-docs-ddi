---
UID: NS:hidpi._HIDP_VALUE_CAPS
title: _HIDP_VALUE_CAPS
author: windows-driver-content
description: The HIDP_VALUE_CAPS structure contains information that describes the capability of a set of HID control values (either a single usage or a usage range).
old-location: hid\hidp_value_caps.htm
old-project: hid
ms.assetid: 37084f3a-f57e-45bb-a364-157b3d155394
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: PHIDP_VALUE_CAPS structure pointer [Human Input Devices], hidpi/PHIDP_VALUE_CAPS, _HIDP_VALUE_CAPS, HIDP_VALUE_CAPS, PHIDP_VALUE_CAPS, hid.hidp_value_caps, HIDP_VALUE_CAPS structure [Human Input Devices], hidpi/HIDP_VALUE_CAPS, *PHIDP_VALUE_CAPS, hidstrct_cbe30aff-5a6a-40d4-9621-b8d93ebb1948.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	hidpi.h
apiname: 
-	HIDP_VALUE_CAPS
product: Windows
targetos: Windows
req.typenames: HIDP_VALUE_CAPS, *PHIDP_VALUE_CAPS
---

# _HIDP_VALUE_CAPS structure


## -description


The HIDP_VALUE_CAPS structure contains information that describes the capability of a set of HID control values (either a single usage or a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage range</a>).


## -syntax


````
typedef struct _HIDP_VALUE_CAPS {
  USAGE   UsagePage;
  UCHAR   ReportID;
  BOOLEAN IsAlias;
  USHORT  BitField;
  USHORT  LinkCollection;
  USAGE   LinkUsage;
  USAGE   LinkUsagePage;
  BOOLEAN IsRange;
  BOOLEAN IsStringRange;
  BOOLEAN IsDesignatorRange;
  BOOLEAN IsAbsolute;
  BOOLEAN HasNull;
  UCHAR   Reserved;
  USHORT  BitSize;
  USHORT  ReportCount;
  USHORT  Reserved2[5];
  ULONG   UnitsExp;
  ULONG   Units;
  LONG    LogicalMin;
  LONG    LogicalMax;
  LONG    PhysicalMin;
  LONG    PhysicalMax;
  union {
    struct {
      USAGE  UsageMin;
      USAGE  UsageMax;
      USHORT StringMin;
      USHORT StringMax;
      USHORT DesignatorMin;
      USHORT DesignatorMax;
      USHORT DataIndexMin;
      USHORT DataIndexMax;
    } Range;
    struct {
      USAGE  Usage;
      USAGE  Reserved1;
      USHORT StringIndex;
      USHORT Reserved2;
      USHORT DesignatorIndex;
      USHORT Reserved3;
      USHORT DataIndex;
      USHORT Reserved4;
    } NotRange;
  };
} HIDP_VALUE_CAPS, *PHIDP_VALUE_CAPS;
````


## -struct-fields




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

Indicates the inclusive lower bound of a sequential range of <a href="https://msdn.microsoft.com/84577544-515a-4fdc-86e5-518182c6c461">data indices</a> that correspond, one-to-one and in the same order, to the usages specified by the usage range <b>Range.UsageMin</b> to <b>Range.UsageMax</b>.


### -field Range.DataIndexMax

Indicates the inclusive upper bound of a sequential range of data indices that correspond, one-to-one and in the same order, to the usages specified by the usage range <b>Range.UsageMin</b> to <b>Range.UsageMax</b>.


### -field NotRange

Specifies, if <b>IsRange</b> is <b>FALSE</b>, information about a single usage. Otherwise, if <b>IsRange</b> is <b>TRUE</b>, <b>Range</b> contains information about a usage range.


### -field NotRange.Reserved1

Reserved for internal system use.


### -field NotRange.Usage

Indicates a <a href="https://msdn.microsoft.com/84fed314-3554-4291-b51c-734d874a4bab">usage ID</a>.


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


### -field UsagePage

Specifies the usage page of the usage or usage range.


### -field ReportID

Specifies the report ID of the HID report that contains the usage or usage range.


### -field IsAlias

Indicates, if <b>TRUE</b>, that the usage is member of a set of aliased usages. Otherwise, if <b>IsAlias</b> is <b>FALSE</b>, the value has only one usage.


### -field BitField

Contains the data fields (one or two bytes) associated with an input, output, or feature main item.


### -field LinkCollection

Specifies the index of the <a href="https://msdn.microsoft.com/3f934661-c33c-4c08-82ac-ee2e0f519c8e">link collection</a> in a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> link collection array that contains the usage or usage range. If <b>LinkCollection</b> is zero, the usage or usage range is contained in the top-level collection.


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

Specifies, if <b>TRUE</b>, that the usage or usage range provides absolute data. Otherwise, if <b>IsAbsolute</b> is <b>FALSE</b>, the value is the change in state from the previous value.


### -field HasNull

Specifies, if <b>TRUE</b>, that the usage supports a <b>NULL</b> value, which indicates that the data is not valid and should be ignored. Otherwise, if <b>HasNull</b> is <b>FALSE</b>, the usage does not have a <b>NULL</b> value.


### -field Reserved

Reserved for internal system use.


### -field BitSize

Specifies the size, in bits, of a usage's data field in a report. If <b>ReportCount</b> is greater than one, each usage has a separate data field of this size.


### -field ReportCount

Specifies the number of usages that this structure describes.


### -field Reserved2

Reserved for internal system use.


### -field UnitsExp

Specifies the usage's exponent, as described by the USB HID standard.


### -field Units

Specifies the usage's units, as described by the USB HID Standard.


### -field LogicalMin

Specifies a usage's signed lower bound.


### -field LogicalMax

Specifies a usage's signed upper bound.


### -field PhysicalMin

Specifies a usage's signed lower bound after scaling is applied to the logical minimum value.


### -field PhysicalMax

Specifies a usage's signed upper bound after scaling is applied to the logical maximum value.


## -remarks


Clients obtain a <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">value capability array</a> by calling <a href="..\hidpi\nf-hidpi-hidp_getvaluecaps.md">HidP_GetValueCaps</a> or <a href="..\hidpi\nf-hidpi-hidp_getspecificvaluecaps.md">HidP_GetSpecificValueCaps</a>. These routines return an array of HIDP_VALUE_CAPS structures in a caller-allocated buffer. The required buffer length is specified in the <a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a> structure returned by <a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>. 

For information about the capabilities of HID control values, see <a href="https://msdn.microsoft.com/228fab4f-ff90-43c5-bc68-26b29e8a7dd6">Collection Capability</a> and <a href="https://msdn.microsoft.com/d447dda6-a1e5-4e57-b06f-f79f8662c236">Value Capability Arrays</a>.



## -see-also

<a href="..\hidpi\nf-hidpi-hidp_getbuttoncaps.md">HidP_GetButtonCaps</a>

<a href="..\hidpi\nf-hidpi-hidp_getusagevaluearray.md">HidP_GetUsageValueArray</a>

<a href="..\hidpi\nf-hidpi-hidp_getspecificvaluecaps.md">HidP_GetSpecificValueCaps</a>

<a href="..\hidpi\nf-hidpi-hidp_getvaluecaps.md">HidP_GetValueCaps</a>

<a href="..\hidpi\nf-hidpi-hidp_getcaps.md">HidP_GetCaps</a>

<a href="..\hidpi\nf-hidpi-hidp_getusagevalue.md">HidP_GetUsageValue</a>

<a href="..\hidpi\nf-hidpi-hidp_getspecificbuttoncaps.md">HidP_GetSpecificButtonCaps</a>

<a href="..\hidpi\ns-hidpi-_hidp_caps.md">HIDP_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_VALUE_CAPS structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

