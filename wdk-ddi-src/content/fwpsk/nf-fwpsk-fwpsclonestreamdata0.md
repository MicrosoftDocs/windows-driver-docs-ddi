---
UID: NF:fwpsk.FwpsCloneStreamData0
title: FwpsCloneStreamData0 function
author: windows-driver-content
description: The FwpsCloneStreamData0 function allocates a clone of an existing FWPS_STREAM_DATA0 data stream.Note  FwpsCloneStreamData0 is a specific version of FwpsCloneStreamData.
old-location: netvista\fwpsclonestreamdata0.htm
old-project: netvista
ms.assetid: 66041ccb-e63a-4843-85ec-d93b924bb335
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsCloneStreamData0, FwpsCloneStreamData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCloneStreamData0, netvista.fwpsclonestreamdata0, wfp_ref_2_funct_3_fwps_C_e155a116-043a-43e5-af71-db0552806978.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Fwpkclnt.lib
-	Fwpkclnt.dll
api_name:
-	FwpsCloneStreamData0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCloneStreamData0 function


## -description


The 
  <b>FwpsCloneStreamData0</b> function allocates a clone of an existing 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a> data stream.
<div class="alert"><b>Note</b>  <b>FwpsCloneStreamData0</b> is a specific version of <b>FwpsCloneStreamData</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param calloutStreamData [in, out]

A pointer to the original 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a> structure that is to
     have its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure cloned.


### -param netBufferListPoolHandle [in, optional]

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff561611">NdisAllocateNetBufferListPool</a> function. This parameter is optional and can be <b>NULL</b>.


### -param netBufferPoolHandle [in, optional]

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> pool handle that was obtained from a
     previous call to the 
     <a href="https://msdn.microsoft.com/bc27758a-a793-48a1-a6ab-bd193aa9c61a">
     NdisAllocateNetBufferPool</a> function. This parameter is optional and can be <b>NULL</b>.


### -param allocateCloneFlags [in]

There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.


### -param netBufferListChain [out]

A pointer to a location that receives a pointer to a chain of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that describe
     all of the cloned stream data.


## -returns



The 
     <b>FwpsCloneStreamData0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The clone 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a> structure was
       successfully allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



This cloned stream data can be injected by a callout driver into the TCP/IP network stack at a later
    time.

The 
    <b>FwpsCloneStreamData0</b> function clones the entire chain of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures contained in the
    existing 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a> data stream. The
    function trims unused data such that a callout driver can successfully pass the cloned chain to the 
    <a href="https://msdn.microsoft.com/d72c3067-21df-40ee-a898-100fcdc5eaca">
    FwpsStreamInjectAsync0</a> function.

After stream data in the clone NET_BUFFER_LIST structure chain has been successfully injected into the
    network stack, the 
    <a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a> callout function is called for
    each clone NET_BUFFER_LIST structure, and a callout should call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a> to
    free the clone NET_BUFFER_LIST structure.

A callout should call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551161">FwpsDiscardClonedStreamData0</a> function if the cloned stream data is to be discarded without being
    reinjected.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551161">FwpsDiscardClonedStreamData0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551213">FwpsStreamInjectAsync0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCloneStreamData0 function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

