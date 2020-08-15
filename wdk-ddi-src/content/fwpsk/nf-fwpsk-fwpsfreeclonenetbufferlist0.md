---
UID: NF:fwpsk.FwpsFreeCloneNetBufferList0
title: FwpsFreeCloneNetBufferList0 function (fwpsk.h)
description: The FwpsFreeCloneNetBufferList0 function frees a clone NET_BUFFER_LIST structure that was previously allocated by a call to the FwpsAllocateCloneNetBufferList0 function.Note  FwpsFreeCloneNetBufferList0 is a specific version of FwpsFreeCloneNetBufferList. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsfreeclonenetbufferlist0.htm
tech.root: netvista
ms.assetid: 0d0dea63-de0d-4421-b123-ce31ac6af1d9
ms.date: 05/02/2018
keywords: ["FwpsFreeCloneNetBufferList0 function"]
ms.keywords: FwpsFreeCloneNetBufferList0, FwpsFreeCloneNetBufferList0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFreeCloneNetBufferList0, netvista.fwpsfreeclonenetbufferlist0, wfp_ref_2_funct_3_fwps_D-H_23efae1d-62cd-4559-b332-08ff843c3ab6.xml
f1_keywords:
 - "fwpsk/FwpsFreeCloneNetBufferList0"
 - "FwpsFreeCloneNetBufferList0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsFreeCloneNetBufferList0
targetos: Windows
req.typenames: 
---

# FwpsFreeCloneNetBufferList0 function


## -description


The 
  <b>FwpsFreeCloneNetBufferList0</b> function frees a clone 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that was previously
  allocated by a call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
  FwpsAllocateCloneNetBufferList0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsFreeCloneNetBufferList0</b> is a specific version of <b>FwpsFreeCloneNetBufferList</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param netBufferList 
[in, out]
A pointer to the clone 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that is being
     freed.


### -param freeCloneFlags 
[in]
There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.


## -remarks



A callout driver calls the 
    <b>FwpsFreeCloneNetBufferList0</b> function to free a clone 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that was
    previously allocated by a call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">FwpsAllocateCloneNetBufferList0</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
   FwpsAllocateCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>
 

 

