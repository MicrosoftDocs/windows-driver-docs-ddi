---
UID: NF:wdm.IoGetDeviceNumaNode
title: IoGetDeviceNumaNode function
author: windows-driver-content
description: The IoGetDeviceNumaNode routine gets the node number of a device.
old-location: kernel\iogetdevicenumanode.htm
old-project: kernel
ms.assetid: a36e9d57-c820-43db-a6e0-e935bffca254
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoGetDeviceNumaNode, IoGetDeviceNumaNode routine [Kernel-Mode Driver Architecture], k104_5a8419d1-9b77-4461-bdc4-9cf5022fb508.xml, kernel.iogetdevicenumanode, wdm/IoGetDeviceNumaNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDeviceNumaNode
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetDeviceNumaNode function


## -description


The <b>IoGetDeviceNumaNode</b> routine gets the node number of a device. 


## -syntax


````
NTSTATUS IoGetDeviceNumaNode(
  _In_  PDEVICE_OBJECT Pdo,
  _Out_ PUSHORT        NodeNumber
);
````


## -parameters




### -param Pdo [in]

A pointer to a physical device object (PDO). This parameter points to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents a physical device. 


### -param NodeNumber [out]

A pointer to a location into which the routine writes the node number, if the node number is known. 


## -returns



<b>IoGetDeviceNumaNode</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The node number of this device is unknown. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Pdo</i> parameter is <b>NULL</b> or does not point to a valid device object. 

</td>
</tr>
</table>
 




## -remarks



In a non-uniform memory access (NUMA) multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

A device (for example, a network controller or storage controller) that is connected to a particular node can access the memory in this node faster than it can access the memory in other nodes. The <i>Pdo</i> parameter points to a PDO that represents the bus connection between the device and the node.

If a NUMA multiprocessor system contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1. To obtain the highest node number, call the <a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine.

After the system is initialized, the node count remains fixed while the system continues to run. This count might include memory-only nodes, which are nodes that contain memory but no active logical processors. A node in which all the logical processors are inactive is effectively a memory-only node until the first processor in the node starts to run. Do not assume that the node that a device is connected to contains active processors.

If a system does not have a NUMA architecture, the routine writes zero to the location that the <i>NodeNumber</i> parameter points to. An example of non-NUMA architecture is a symmetric multiprocessor system (SMP). 




## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetDeviceNumaNode routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

