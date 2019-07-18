---
UID: NF:ndis.NdisSystemActiveProcessorCount
title: NdisSystemActiveProcessorCount function (ndis.h)
description: The NdisSystemActiveProcessorCount function returns the number of currently active processors in the local computer.
old-location: netvista\ndissystemactiveprocessorcount.htm
tech.root: netvista
ms.assetid: 7ddb54eb-9f20-4cb9-8488-5f2806d23430
ms.date: 05/02/2018
ms.keywords: NdisSystemActiveProcessorCount, NdisSystemActiveProcessorCount function [Network Drivers Starting with Windows Vista], ndis/NdisSystemActiveProcessorCount, ndis_sysinfo_ref_f69290a6-03f9-4fe8-bc02-6f58a650fa00.xml, netvista.ndissystemactiveprocessorcount
ms.topic: function
f1_keywords:
 - "ndis/NdisSystemActiveProcessorCount"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.1. For NDIS 6.20 and later, use NdisGroupActiveProcessorCount instead.
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisSystemActiveProcessorCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisSystemActiveProcessorCount function


## -description


The 
  <b>NdisSystemActiveProcessorCount</b> function returns the number of currently active processors in the
  local computer.


## -parameters




### -param ActiveProcessors

A pointer to a 
     [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed variable that receives a bitmap
     that represents the set of currently active processors. In a hot-add environment, this bitmap can change
     during runtime.


## -returns



<b>NdisSystemActiveProcessorCount</b> returns the number of currently active processors in the local
     computer.




## -remarks



An NDIS driver might call the 
    <b>NdisSystemActiveProcessorCount</b> function during initialization before it allocates resources.

<b>NdisSystemActiveProcessorCount</b> is similar to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kequeryactiveprocessorcount">
    KeQueryActiveProcessorCount</a> function.

<div class="alert"><b>Note</b>  NDIS drivers should not use 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a> to
    retrieve the number of currently active processors,</div>
<div> </div>
<div class="alert"><b>Note</b>  <b>NdisSystemActiveProcessorCount</b> might not map processors to the bits in the returned 
    [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value consecutively. and 
    <b>NdisSystemActiveProcessorCount</b> might not return the same bitmap every time that it is
    called.</div>
<div> </div>
The value that 
    <b>NdisSystemActiveProcessorCount</b> returns can change at runtime on SKUs that support hot-add CPU
    functionality.

The Windows Server 2008 Enterprise operating system and the Windows Server 2008 Datacenter operating
    system support 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dynamic-hardware-partitioning-architecture">dynamic hardware
    partitioning</a>. As part of dynamic hardware partitioning, Windows Server 2008 supports hot-add
    operations for CPUs at runtime. In a hot-add CPU environment, the number of processors might not remain
    constant during runtime.




## -see-also




[**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kequeryactiveprocessorcount">KeQueryActiveProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisgroupactiveprocessorcount">NdisGroupActiveProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndissystemprocessorcount">NdisSystemProcessorCount</a>
 

 

