---
UID: NF:ndis.NdisSystemActiveProcessorCount
title: NdisSystemActiveProcessorCount function
author: windows-driver-content
description: The NdisSystemActiveProcessorCount function returns the number of currently active processors in the local computer.
old-location: netvista\ndissystemactiveprocessorcount.htm
old-project: netvista
ms.assetid: 7ddb54eb-9f20-4cb9-8488-5f2806d23430
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndissystemactiveprocessorcount, NdisSystemActiveProcessorCount function [Network Drivers Starting with Windows Vista], NdisSystemActiveProcessorCount, ndis/NdisSystemActiveProcessorCount, ndis_sysinfo_ref_f69290a6-03f9-4fe8-bc02-6f58a650fa00.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisSystemActiveProcessorCount
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisSystemActiveProcessorCount function


## -description


The 
  <b>NdisSystemActiveProcessorCount</b> function returns the number of currently active processors in the
  local computer.


## -syntax


````
ULONG NdisSystemActiveProcessorCount(
   PKAFFINITY ActiveProcessors
);
````


## -parameters




### -param ActiveProcessors

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that receives a bitmap
     that represents the set of currently active processors. In a hot-add environment, this bitmap can change
     during runtime.


## -returns



<b>NdisSystemActiveProcessorCount</b> returns the number of currently active processors in the local
     computer.




## -remarks



An NDIS driver might call the 
    <b>NdisSystemActiveProcessorCount</b> function during initialization before it allocates resources.

<b>NdisSystemActiveProcessorCount</b> is similar to the 
    <a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">
    KeQueryActiveProcessorCount</a> function.

<div class="alert"><b>Note</b>  NDIS drivers should not use 
    <a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a> to
    retrieve the number of currently active processors,</div>
<div> </div>
<div class="alert"><b>Note</b>  <b>NdisSystemActiveProcessorCount</b> might not map processors to the bits in the returned 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a> value consecutively. and 
    <b>NdisSystemActiveProcessorCount</b> might not return the same bitmap every time that it is
    called.</div>
<div> </div>
The value that 
    <b>NdisSystemActiveProcessorCount</b> returns can change at runtime on SKUs that support hot-add CPU
    functionality.

The Windows Server 2008 Enterprise operating system and the Windows Server 2008 Datacenter operating
    system support 
    <a href="https://msdn.microsoft.com/1b6a1dc5-ec32-4bb9-acaf-14db284b4a0e">dynamic hardware
    partitioning</a>. As part of dynamic hardware partitioning, Windows Server 2008 supports hot-add
    operations for CPUs at runtime. In a hot-add CPU environment, the number of processors might not remain
    constant during runtime.




## -see-also

<a href="..\ndis\nf-ndis-ndisgroupactiveprocessorcount.md">NdisGroupActiveProcessorCount</a>



<a href="..\ndis\nf-ndis-ndissystemprocessorcount.md">NdisSystemProcessorCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>



<a href="..\wdm\nf-wdm-kequeryactiveprocessorcount.md">KeQueryActiveProcessorCount</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSystemActiveProcessorCount function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

