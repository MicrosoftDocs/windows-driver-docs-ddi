---
UID: NF:ndis.NdisMoveMemory
title: NdisMoveMemory macro
author: windows-driver-content
description: The NdisMoveMemory function copies a specified number of bytes from one caller-supplied location to another.
old-location: netvista\ndismovememory.htm
old-project: netvista
ms.assetid: 1be08720-be44-4e1b-b0ec-b4eb0a2718a0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMoveMemory, NdisMoveMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisMoveMemory, ndis_memory_ref_19f420d5-3747-48fa-a6c6-d1088449075b.xml, netvista.ndismovememory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlCopyMemory (not RtlMoveMemory) instead.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMoveMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMoveMemory macro


## -description


The 
  <b>NdisMoveMemory</b> function copies a specified number of bytes from one caller-supplied location to
  another.


## -syntax


````
VOID NdisMoveMemory(
  [out] PVOID Destination,
  [in]  PVOID Source,
  [in]  ULONG Length
);
````


## -parameters




### -param Destination [out]

A pointer to a system-space buffer that is the destination of the move. This buffer must be at
     least 
     <i>Length</i> bytes in size.


### -param Source [in]

A pointer to a system-space buffer from which this function copies the data to the destination
     buffer. This buffer must be at least 
     <i>Length</i> bytes in size.


### -param Length [in]

The number of bytes to copy.


## -remarks



Both 
    <i>Source</i> and 
    <i>Destination</i> are virtual addresses.

If either address falls within a range of device memory that was mapped with 
    <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>, a miniport driver should
    call one of the 
    <b>Ndis..MappedMemory</b> functions instead of 
    <b>NdisMoveMemory</b>.

The range specified by 
    <i>Source</i> and 
    <i>Length</i> cannot overlap the 
    <i>Destination</i> range.

Callers of 
    <b>NdisMoveMemory</b> can run at any IRQL if the given 
    <i>Source</i> and 
    <i>Destination</i> are resident. Otherwise, callers must be running at IRQL &lt; DISPATCH_LEVEL, as, for
    example if either address is on the stack.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
   NdisAllocateMemoryWithTagPriority</a>



<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMoveMemory macro%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

