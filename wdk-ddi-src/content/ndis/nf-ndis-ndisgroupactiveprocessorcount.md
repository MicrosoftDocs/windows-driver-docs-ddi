---
UID: NF:ndis.NdisGroupActiveProcessorCount
title: NdisGroupActiveProcessorCount function (ndis.h)
description: The NdisGroupActiveProcessorCount function returns the number of processors that are currently active in a specified group.
old-location: netvista\ndisgroupactiveprocessorcount.htm
tech.root: netvista
ms.assetid: d6631aa7-e3ba-4768-a55a-6a66d1ee84c6
ms.date: 05/02/2018
ms.keywords: NdisGroupActiveProcessorCount, NdisGroupActiveProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisGroupActiveProcessorCount, ndis_processor_group_ref_43adb4cc-e1a6-4a67-ada7-47b38078e357.xml, netvista.ndisgroupactiveprocessorcount
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGroupActiveProcessorCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisGroupActiveProcessorCount function


## -description


The 
  <b>NdisGroupActiveProcessorCount</b> function returns the number of processors that are currently active in
  a specified group.


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
    <a href="https://msdn.microsoft.com/92a50a96-8bfb-4d5d-8f24-dd29794e55b1">
    NdisGroupActiveProcessorMask</a> returns can change at runtime on SKUs that support hot-add
    functionality for CPUs.

<div class="alert"><b>Note</b>  NDIS drivers should not use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a> function
    to retrieve the number of processors that are currently active. Also, NDIS 6.20 drivers should not use
    the 
    <a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
    NdisSystemActiveProcessorCount</a> function because it only returns the processor count and provides
    the affinity mask as an out parameter, for processor group 0.</div>
<div> </div>
To obtain an active affinity mask, call the 
    <a href="https://msdn.microsoft.com/92a50a96-8bfb-4d5d-8f24-dd29794e55b1">
    NdisGroupActiveProcessorMask</a> function.

To obtain the maximum number of processors in a group, call the 
    <a href="https://msdn.microsoft.com/545a5014-aa07-49ee-92b7-2ae95f4ce785">
    NdisGroupMaxProcessorCount</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562687">NdisGroupActiveProcessorMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562689">NdisGroupMaxProcessorCount</a>



<a href="https://msdn.microsoft.com/7ddb54eb-9f20-4cb9-8488-5f2806d23430">
   NdisSystemActiveProcessorCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564579">NdisSystemProcessorCount</a>
 

 

