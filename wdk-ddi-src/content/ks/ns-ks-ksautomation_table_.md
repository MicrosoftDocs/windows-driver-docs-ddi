---
UID: NS:ks.KSAUTOMATION_TABLE_
title: KSAUTOMATION_TABLE_
author: windows-driver-content
description: The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.
old-location: stream\ksautomation_table.htm
old-project: stream
ms.assetid: 76ab776d-0921-4fdb-9646-2cb97a582f6e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSAUTOMATION_TABLE, ,, A, B, E, I, K, KSAUTOMATION_TABLE, KSAUTOMATION_TABLE structure [Streaming Media Devices], KSAUTOMATION_TABLE_, L, M, N, O, P, PKSAUTOMATION_TABLE, PKSAUTOMATION_TABLE structure pointer [Streaming Media Devices], S, T, U, _, avstruct_7389df5c-d86a-43b2-9daf-d0e1e8a2dfbe.xml, ks/KSAUTOMATION_TABLE, ks/PKSAUTOMATION_TABLE, stream.ksautomation_table"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSAUTOMATION_TABLE
product: Windows
targetos: Windows
req.typenames: KSAUTOMATION_TABLE, *PKSAUTOMATION_TABLE
---

# KSAUTOMATION_TABLE_ structure


## -description


The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.


## -syntax


````
typedef struct KSAUTOMATION_TABLE_ {
  ULONG                PropertySetsCount;
  ULONG                PropertyItemSize;
  const KSPROPERTY_SET *PropertySets;
  ULONG                MethodSetsCount;
  ULONG                MethodItemSize;
  const KSMETHOD_SET   *MethodSets;
  ULONG                EventSetsCount;
  ULONG                EventItemSize;
  const KSEVENT_SET    *EventSets;
  PVOID                Alignment;
} KSAUTOMATION_TABLE, *PKSAUTOMATION_TABLE;
````


## -struct-fields




### -field PropertySetsCount

This member specifies the number of property sets in this automation table.


### -field PropertyItemSize

This member specifies size in bytes of property items in this table.


### -field PropertySets

A pointer to an array of <a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a> objects (<b>PropertySetsCount</b> in length) defining the property sets in this automation table.  Each set contains a specific number of items of size <b>PropertyItemSize</b>.


### -field MethodSetsCount

This member specifies the number of method sets in this automation table.


### -field MethodItemSize

This member specifies the size in bytes of method items in this table.


### -field MethodSets

An array of <a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a> objects (<b>MethodSetsCount</b> in length) defining the method sets in this automation table.  Each set has a specific number of items in it of size <b>MethodItemSize</b>.


### -field EventSetsCount

This member specifies the number of event sets in this automation table.


### -field EventItemSize

This member specifies the size in bytes of event items in this table.


### -field EventSets

An array of <a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a> objects (<b>EventSetsCount</b> in length) defining the event sets in this automation table.  Each set has a specific number of items in it of size <b>EventItemSize</b>.


### -field Alignment

Reserved for internal use by AVStream. Minidrivers should not manipulate this member. 


## -remarks



Note that each object (pin, filter, topology node) should define an automation table. Minidrivers can use macros defined in <i>Ks.h</i> to define automation tables and the arrays they contain:

DEFINE_KSAUTOMATION_TABLE

DEFINE_KSAUTOMATION_PROPERTIES

DEFINE_KSAUTOMATION_METHODS

DEFINE_KSAUTOMATION_EVENTS

To specify an automation table containing an empty property array, event array, or method array:

DEFINE_KSAUTOMATION_PROPERTIES_NULL

DEFINE_KSAUTOMATION_METHODS_NULL

DEFINE_KSAUTOMATION_EVENTS_NULL

For example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_KSAUTOMATION_TABLE (MyAutomationTable) {
DEFINE_KSAUTOMATION_PROPERTIES (MyPropertyTable),
DEFINE_KSAUTOMATION_METHODS (MyMethodTable),
DEFINE_KSAUTOMATION_EVENTS (MyEventTable)</pre>
</td>
</tr>
</table></span></div>
};




## -see-also

<a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a>



<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>



<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>



<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>



<a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a>



<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSAUTOMATION_TABLE structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

