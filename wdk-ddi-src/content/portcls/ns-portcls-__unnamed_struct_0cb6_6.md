---
UID: NS:portcls.__unnamed_struct_0cb6_6
title: PCAUTOMATION_TABLE
author: windows-driver-content
description: The PCAUTOMATION_TABLE structure contains a miniport driver's master table of properties, methods, and events.
old-location: audio\pcautomation_table.htm
tech.root: audio
ms.assetid: 9761a967-063d-4194-8b67-eec476d3372e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PPCAUTOMATION_TABLE, PCAUTOMATION_TABLE, PCAUTOMATION_TABLE structure [Audio Devices], PPCAUTOMATION_TABLE, PPCAUTOMATION_TABLE structure pointer [Audio Devices], audio.pcautomation_table, audpc-struct_2322a469-8fd0-4c56-b8d2-df6cf8b8d1dd.xml, portcls/PCAUTOMATION_TABLE, portcls/PPCAUTOMATION_TABLE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: portcls.h
req.include-header: Portcls.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	portcls.h
api_name:
-	PCAUTOMATION_TABLE
product:
- Windows
targetos: Windows
req.typenames: PCAUTOMATION_TABLE, *PPCAUTOMATION_TABLE
---

# PCAUTOMATION_TABLE structure


## -description


The <b>PCAUTOMATION_TABLE</b> structure contains a miniport driver's master table of properties, methods, and events.


## -syntax


```cpp
typedef struct {
  ULONG                 PropertyItemSize;
  ULONG                 PropertyCount;
  const PCPROPERTY_ITEM *Properties;
  ULONG                 MethodItemSize;
  ULONG                 MethodCount;
  const PCMETHOD_ITEM   *Methods;
  ULONG                 EventItemSize;
  ULONG                 EventCount;
  const PCEVENT_ITEM    *Events;
  ULONG                 Reserved;
} PCAUTOMATION_TABLE, *PPCAUTOMATION_TABLE;
```


## -struct-fields




### -field PropertyItemSize

Specifies the size in bytes of the property structure used. Set this member to <b>sizeof</b>(PCPROPERTY_ITEM) or greater. See the following Remarks section.


### -field PropertyCount

Specifies the number of property items in the <i>Properties</i> array.


### -field Properties

Pointer to the filter's array of properties. This is an array of <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md">PCPROPERTY_ITEM</a> structures.


### -field MethodItemSize

Specifies the size in bytes of the methods structure used. Set this member to <b>sizeof</b>(PCMETHOD_ITEM) or greater. See the following Remarks section.


### -field MethodCount

Specifies the number of method items in the <b>Methods</b> array.


### -field Methods

Pointer to the filter's array of methods. This is an array of <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_4.md">PCMETHOD_ITEM</a> structures.


### -field EventItemSize

Specifies the size in bytes of the event structure used. Set this member to <b>sizeof</b>(PCEVENT_ITEM) or greater. See the following Remarks section.


### -field EventCount

Specifies the number of event items in the <b>Events</b> array.


### -field Events

Pointer to the filter's array of events. This is an array of <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_5.md">PCEVENT_ITEM</a> structures.


### -field Reserved

Reserved. Initialize to zero.


## -remarks



Any of the structure's item pointers can be <b>NULL</b>, in which case the corresponding counts should be zero. For item tables that are not zero length, the item size should not be smaller than the size of the corresponding item structure that is defined in the header file portcls.h. The minimum size for a property, event, or method item is <b>sizeof</b>(PCPROPERTY_ITEM), <b>sizeof</b>(PCEVENT_ITEM), or <b>sizeof</b>(PCMETHOD_ITEM), respectively. The item size can be larger than this, in which case the item structure is followed by whatever private data the miniport driver appends to it. Item sizes should be a multiple of eight.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method outputs a <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_9.md">PCFILTER_DESCRIPTOR</a> structure that points to a PCAUTOMATION_TABLE structure that specifies the miniport driver's automation table.




## -see-also

<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_4.md">PCMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_3.md">PCPROPERTY_ITEM</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_9.md">PCFILTER_DESCRIPTOR</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_5.md">PCEVENT_ITEM</a>



 

 


