---
UID: NS:wmistr.tagWNODE_SINGLE_INSTANCE
title: tagWNODE_SINGLE_INSTANCE
author: windows-driver-content
description: The WNODE_SINGLE_INSTANCE structure contains values for all data items in one instance of a data block.
old-location: kernel\wnode_single_instance.htm
old-project: kernel
ms.assetid: 03e922af-f42a-4801-adc5-fc7a0b90f4a7
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE, PWNODE_SINGLE_INSTANCE structure pointer [Kernel-Mode Driver Architecture], WNODE_SINGLE_INSTANCE, WNODE_SINGLE_INSTANCE structure [Kernel-Mode Driver Architecture], kernel.wnode_single_instance, kstruct_d_c6ae2ea3-5e64-466d-b479-02a9eea71b20.xml, tagWNODE_SINGLE_INSTANCE, wmistr/PWNODE_SINGLE_INSTANCE, wmistr/WNODE_SINGLE_INSTANCE"
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
-	WNODE_SINGLE_INSTANCE
product: Windows
targetos: Windows
req.typenames: WNODE_SINGLE_INSTANCE, *PWNODE_SINGLE_INSTANCE
req.product: Windows 10 or later.
---

# tagWNODE_SINGLE_INSTANCE structure


## -description


The <b>WNODE_SINGLE_INSTANCE</b> structure contains values for all data items in one instance of a data block.


## -syntax


````
typedef struct tagWNODE_SINGLE_INSTANCE {
  struct _WNODE_HEADER  WnodeHeader;
  ULONG                OffsetInstanceName;
  ULONG                InstanceIndex;
  ULONG                DataBlockOffset;
  ULONG                SizeDataBlock;
  UCHAR                VariableData[];
} WNODE_SINGLE_INSTANCE, *PWNODE_SINGLE_INSTANCE;
````


## -struct-fields




### -field WnodeHeader

Is a <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


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



WMI passes a <b>WNODE_SINGLE_INSTANCE</b> with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request to set read/write data items in an instance of a data block. A driver can ignore values passed for read-only data items in the instance.

A driver fills in a <b>WNODE_SINGLE_INSTANCE</b> in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551718">IRP_MN_QUERY_SINGLE_INSTANCE</a> request or to generate an event that consists of a single instance.




## -see-also

<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>



<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WNODE_SINGLE_INSTANCE structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

