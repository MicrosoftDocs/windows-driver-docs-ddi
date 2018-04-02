---
UID: NF:ndis.NdisGetProcessorInformationEx
title: NdisGetProcessorInformationEx function
author: windows-driver-content
description: The NdisGetProcessorInformationEx function retrieves information about the CPU topology of the local computer.
old-location: netvista\ndisgetprocessorinformationex.htm
old-project: netvista
ms.assetid: 9af21f56-d93d-4130-888c-c7009dc2854d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetProcessorInformationEx, NdisGetProcessorInformationEx function [Network Drivers Starting with Windows Vista], ndis/NdisGetProcessorInformationEx, ndis_processor_group_ref_f387710b-fb49-4202-9ff5-496021972695.xml, netvista.ndisgetprocessorinformationex
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetProcessorInformationEx
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetProcessorInformationEx function


## -description


The 
  <b>NdisGetProcessorInformationEx</b> function retrieves information about the CPU topology of the local
  computer.


## -parameters




### -param NdisHandle [in, optional]

An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> functions.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



### -param SystemProcessorInfo [out, optional]

A pointer to a caller-allocated buffer where NDIS puts the 
     <a href="https://msdn.microsoft.com/ba3c6641-98bc-4c44-9889-7583c4cf61f0">
     NDIS_SYSTEM_PROCESSOR_INFO_EX</a> structure and an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566811">NDIS_PROCESSOR_INFO_EX</a> structures
     that contain information about the CPU topology of the local computer. The caller provides the length of
     the buffer in the 
     <i>Size</i> parameter.


### -param Size [in, out]

A pointer to a value that is the size, in bytes, of the buffer that the caller provided. When the
     function returns, this value contains either the amount of data that NDIS put in the buffer or the
     required size of the buffer if the buffer was too short.


## -returns



<b>NdisGetProcessorInformationEx</b> can return one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer at the 
       <i>Size</i> parameter was too small. In this case, NDIS provides the required buffer size in the 
       <i>Size</i> member.

</td>
</tr>
</table>
 




## -remarks



NDIS drivers call the 
    <b>NdisGetProcessorInformationEx</b> function to retrieve information about the processors on the local
    computer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567872">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
 

 

