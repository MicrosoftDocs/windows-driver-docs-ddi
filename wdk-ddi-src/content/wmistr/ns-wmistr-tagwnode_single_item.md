---
UID: NS:wmistr.tagWNODE_SINGLE_ITEM
title: tagWNODE_SINGLE_ITEM
author: windows-driver-content
description: The WNODE_SINGLE_ITEM structure contains the value of a single data item in an instance of a data block.
old-location: kernel\wnode_single_item.htm
old-project: kernel
ms.assetid: 65b64678-09dc-4bc2-8362-d15eba5a828a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: tagWNODE_SINGLE_ITEM, wmistr/WNODE_SINGLE_ITEM, WNODE_SINGLE_ITEM, kernel.wnode_single_item, kstruct_d_49c197d8-c13f-4ca7-b82f-e56282eac847.xml, wmistr/PWNODE_SINGLE_ITEM, WNODE_SINGLE_ITEM structure [Kernel-Mode Driver Architecture], *PWNODE_SINGLE_ITEM, PWNODE_SINGLE_ITEM structure pointer [Kernel-Mode Driver Architecture], PWNODE_SINGLE_ITEM
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wmistr.h
apiname:
-	WNODE_SINGLE_ITEM
product: Windows
targetos: Windows
req.typenames: WNODE_SINGLE_ITEM, *PWNODE_SINGLE_ITEM
req.product: Windows 10 or later.
---

# tagWNODE_SINGLE_ITEM structure


## -description


The <b>WNODE_SINGLE_ITEM</b> structure contains the value of a single data item in an instance of a data block.


## -syntax


````
typedef struct tagWNODE_SINGLE_ITEM {
  struct _WNODE_HEADER  WnodeHeader;
  ULONG                OffsetInstanceName;
  ULONG                InstanceIndex;
  ULONG                ItemId;
  ULONG                DataBlockOffset;
  ULONG                SizeDataItem;
  UCHAR                VariableData[];
} WNODE_SINGLE_ITEM, *PWNODE_SINGLE_ITEM;
````


## -struct-fields




### -field WnodeHeader

Is a <a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a> structure that contains information common to all <b>WNODE_<i>XXX</i></b> structures, such as the buffer size, the GUID that represents a data block associated with a request, and flags that provide information about the <b>WNODE_<i>XXX</i></b> data being passed or returned.


### -field _WNODE_HEADER

 


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

<a href="..\wmistr\ns-wmistr-_wnode_header.md">WNODE_HEADER</a>



<a href="..\wmistr\ns-wmistr-tagwnode_event_item.md">WNODE_EVENT_ITEM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WNODE_SINGLE_ITEM structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

