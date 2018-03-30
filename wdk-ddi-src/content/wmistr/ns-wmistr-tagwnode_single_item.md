---
UID: NS:wmistr.tagWNODE_SINGLE_ITEM
title: tagWNODE_SINGLE_ITEM
author: windows-driver-content
description: The WNODE_SINGLE_ITEM structure contains the value of a single data item in an instance of a data block.
old-location: kernel\wnode_single_item.htm
old-project: kernel
ms.assetid: 65b64678-09dc-4bc2-8362-d15eba5a828a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PWNODE_SINGLE_ITEM, PWNODE_SINGLE_ITEM, PWNODE_SINGLE_ITEM structure pointer [Kernel-Mode Driver Architecture], WNODE_SINGLE_ITEM, WNODE_SINGLE_ITEM structure [Kernel-Mode Driver Architecture], kernel.wnode_single_item, kstruct_d_49c197d8-c13f-4ca7-b82f-e56282eac847.xml, tagWNODE_SINGLE_ITEM, wmistr/PWNODE_SINGLE_ITEM, wmistr/WNODE_SINGLE_ITEM"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmistr.h
req.include-header: Wmistr.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wmistr.h
api_name:
-	WNODE_SINGLE_ITEM
product: Windows
targetos: Windows
req.typenames: WNODE_SINGLE_ITEM, *PWNODE_SINGLE_ITEM
req.product: Windows 10 or later.
---

# tagWNODE_SINGLE_ITEM structure


## -description


The <b>WNODE_SINGLE_ITEM</b> structure contains the value of a single data item in an instance of a data block.


## -struct-fields




### -field WnodeHeader

Is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field OffsetInstanceName

Indicates the offset from the beginning of this structure to the dynamic instance name, if any, aligned on a USHORT boundary. This member is valid only if WNODE_FLAG_STATIC_INSTANCE_NAMES is clear in <b>WnodeHeader.Flags</b>. If the data block was registered with static instance names, WMI ignores <b>OffsetInstanceName</b>. 


### -field InstanceIndex

Indicates the index into the driver's list of static instance names of this instance. This member is valid only if the data block was registered with static instance names and WNODE_FLAG_STATIC_INSTANCE_NAMES is set in <b>WnodeHeader.Flags</b>. If the data block was registered with dynamic instance names, WMI ignores <b>InstanceIndex</b>. 


### -field ItemId

Specifies the ID of the data item to set.


### -field DataBlockOffset

Indicates the offset from the beginning of this structure to the new value for the data item. 


### -field SizeDataItem

Indicates the size of the data item.


### -field VariableData

Contains additional data, including the dynamic instance name if any, padding so the data value begins on an 8-byte boundary, and the new value for the data item. 


## -remarks



WMI passes a <b>WNODE_SINGLE_ITEM</b> with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550836">IRP_MN_CHANGE_SINGLE_ITEM</a> request to set the value of a data item in an instance of a data block.

A driver builds a <b>WNODE_SINGLE_ITEM</b> to generate an event that consists of a single data item.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566373">WNODE_EVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566375">WNODE_HEADER</a>
 

 

