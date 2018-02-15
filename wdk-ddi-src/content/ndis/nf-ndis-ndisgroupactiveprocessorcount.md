---
UID: NF:ndis.NdisGroupActiveProcessorCount
title: NdisGroupActiveProcessorCount function
author: windows-driver-content
description: The NdisGroupActiveProcessorCount function returns the number of processors that are currently active in a specified group.
old-location: netvista\ndisgroupactiveprocessorcount.htm
old-project: netvista
ms.assetid: d6631aa7-e3ba-4768-a55a-6a66d1ee84c6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisGroupActiveProcessorCount, netvista.ndisgroupactiveprocessorcount, NdisGroupActiveProcessorCount function [Network Drivers Starting with Windows Vista], ndis_processor_group_ref_43adb4cc-e1a6-4a67-ada7-47b38078e357.xml, NdisGroupActiveProcessorCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisGroupActiveProcessorCount
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisGroupActiveProcessorCount function


## -description


The 
  <b>NdisGroupActiveProcessorCount</b> function returns the number of processors that are currently active in
  a specified group.


## -syntax


````
ULONG NdisGroupActiveProcessorCount(
   USHORT Group
);
````


## -parameters




### -param Group

A USHORT value that identifies a processor group in the local computer system.


## -returns



<b>NdisGroupActiveProcessorCount</b> returns a ULONG value for the number of processors that are active
      in the group that is specified in the 
      <i>Group</i> parameter. The number of processors is a zero-based value.

If the 
      <i>Group</i> parameter is ALL_PROCESSOR_GROUPS, 
      <b>NdisGroupActiveProcessorCount</b> returns the number of active processors in the local computer.




## -remarks



An NDIS driver might call the 
    <b>NdisGroupActiveProcessorCount</b> function during initialization before it allocates resources.

The processor count that 
    <a href="..\ndis\nf-ndis-ndisgroupactiveprocessormask.md">
    NdisGroupActiveProcessorMask</a> returns can change at runtime on SKUs that support hot-add
    functionality for CPUs.

<div class="alert"><b>Note</b>  NDIS drivers should not use the 
    <a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a> function
    to retrieve the number of processors that are currently active. Also, NDIS 6.20 drivers should not use
    the 
    <a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
    NdisSystemActiveProcessorCount</a> function because it only returns the processor count and provides
    the affinity mask as an out parameter, for processor group 0.</div>
<div> </div>
To obtain an active affinity mask, call the 
    <a href="..\ndis\nf-ndis-ndisgroupactiveprocessormask.md">
    NdisGroupActiveProcessorMask</a> function.

To obtain the maximum number of processors in a group, call the 
    <a href="..\ndis\nf-ndis-ndisgroupmaxprocessorcount.md">
    NdisGroupMaxProcessorCount</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndisgroupmaxprocessorcount.md">NdisGroupMaxProcessorCount</a>



<a href="..\ndis\nf-ndis-ndisgroupactiveprocessormask.md">NdisGroupActiveProcessorMask</a>



<a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a>



<a href="..\ndis\nf-ndis-ndissystemactiveprocessorcount.md">
   NdisSystemActiveProcessorCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGroupActiveProcessorCount function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

