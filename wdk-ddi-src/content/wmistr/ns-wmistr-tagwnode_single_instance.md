---
UID: NS:wmistr.tagWNODE_SINGLE_INSTANCE
title: tagWNODE_SINGLE_INSTANCE (wmistr.h)
description: The WNODE_SINGLE_INSTANCE structure contains values for all data items in one instance of a data block.
old-location: kernel\wnode_single_instance.htm
tech.root: kernel
ms.assetid: 03e922af-f42a-4801-adc5-fc7a0b90f4a7
ms.date: 04/30/2018
ms.keywords: "*PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE structure pointer [Kernel-Mode Driver Architecture], WNODE_SINGLE_INSTANCE, WNODE_SINGLE_INSTANCE structure [Kernel-Mode Driver Architecture], kernel.wnode_single_instance, kstruct_d_c6ae2ea3-5e64-466d-b479-02a9eea71b20.xml, tagWNODE_SINGLE_INSTANCE, wmistr/PWNODE_SINGLE_INSTANCE, wmistr/WNODE_SINGLE_INSTANCE"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wmistr.h
api_name:
- WNODE_SINGLE_INSTANCE
product:
- Windows
targetos: Windows
req.typenames: WNODE_SINGLE_INSTANCE, *PWNODE_SINGLE_INSTANCE
---

# tagWNODE_SINGLE_INSTANCE structure


## -description


The <b>WNODE_SINGLE_INSTANCE</b> structure contains values for all data items in one instance of a data block.


## -struct-fields




### -field WnodeHeader

Is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field OffsetInstanceName

Indicates the offset from the beginning of this structure to the dynamic instance name of this instance, aligned on a USHORT boundary. This member is valid only if WNODE_FLAG_STATIC_INSTANCE_NAMES is clear in <b>WnodeHeader.Flags</b>. If the data block was registered with static instance names, WMI ignores <b>OffsetInstanceName</b>.


### -field InstanceIndex

Indicates the index of an instance registered with static instance names. This member is valid only if WNODE_FLAG_STATIC_INSTANCE_NAMES is set in <b>WnodeHeader.Flags</b>. If the data block was registered with dynamic instance names, WMI ignores <b>InstanceIndex</b>.


### -field DataBlockOffset

Indicates the offset from the beginning of this structure to the beginning of the instance. 


### -field SizeDataBlock

Indicates the size of the data block for this instance.


### -field VariableData

Contains additional data, including the dynamic instance name if any, padding so the instance begins on an 8-byte boundary, and the instance of the data block to be returned. 


## -remarks



WMI passes a <b>WNODE_SINGLE_INSTANCE</b> with an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-change-single-instance">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to set read/write data items in an instance of a data block. A driver can ignore values passed for read-only data items in the instance.

A driver fills in a <b>WNODE_SINGLE_INSTANCE</b> in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-single-instance">IRP_MN_QUERY_SINGLE_INSTANCE</a> request or to generate an event that consists of a single instance.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-tagwnode_event_item">WNODE_EVENT_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wmistr/ns-wmistr-_wnode_header">WNODE_HEADER</a>
 

 

