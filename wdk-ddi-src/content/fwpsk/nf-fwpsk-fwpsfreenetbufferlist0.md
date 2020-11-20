---
UID: NF:fwpsk.FwpsFreeNetBufferList0
title: FwpsFreeNetBufferList0 function (fwpsk.h)
description: The FwpsFreeNetBufferList0 function frees a NET_BUFFER_LIST structure that was previously allocated by a call to the FwpsAllocateNetBufferAndNetBufferList0 function.Note  FwpsFreeNetBufferList0 is a specific version of FwpsFreeNetBufferList.
old-location: netvista\fwpsfreenetbufferlist0.htm
tech.root: netvista
ms.assetid: 7e337d7a-a408-4574-8da3-ea333fdbde8b
ms.date: 05/02/2018
keywords: ["FwpsFreeNetBufferList0 function"]
ms.keywords: FwpsFreeNetBufferList0, FwpsFreeNetBufferList0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsFreeNetBufferList0, netvista.fwpsfreenetbufferlist0, wfp_ref_2_funct_3_fwps_D-H_2104bcba-b5f2-4476-9b9e-9783269618f0.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsFreeNetBufferList0
 - fwpsk/FwpsFreeNetBufferList0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsFreeNetBufferList0
---

# FwpsFreeNetBufferList0 function


## -description

The 
  <b>FwpsFreeNetBufferList0</b> function frees a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that was previously
  allocated by a call to the 
  <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">FwpsAllocateNetBufferAndNetBufferList0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsFreeNetBufferList0</b> is a specific version of <b>FwpsFreeNetBufferList</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param netBufferList 

[in, out]
A pointer to the 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that is being
     freed.

## -remarks

A callout driver calls the 
    <b>FwpsFreeNetBufferList0</b> function to free a 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that was
    previously allocated by a call to the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">FwpsAllocateNetBufferAndNetBufferList0</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>