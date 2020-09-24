---
UID: NF:fwpsk.FwpsDiscardClonedStreamData0
title: FwpsDiscardClonedStreamData0 function (fwpsk.h)
description: The FwpsDiscardClonedStreamData0 function frees the memory buffer that is allocated by the FwpsCloneStreamData0 function.Note  FwpsDiscardClonedStreamData0 is a specific version of FwpsDiscardClonedStreamData.
old-location: netvista\fwpsdiscardclonedstreamdata0.htm
tech.root: netvista
ms.assetid: 11e8338d-4ca3-49a4-8cfe-ac9f15434b4f
ms.date: 05/02/2018
keywords: ["FwpsDiscardClonedStreamData0 function"]
ms.keywords: FwpsDiscardClonedStreamData0, FwpsDiscardClonedStreamData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsDiscardClonedStreamData0, netvista.fwpsdiscardclonedstreamdata0, wfp_ref_2_funct_3_fwps_D-H_b09851bf-8f28-4f16-8c7d-b6f89b276845.xml
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsDiscardClonedStreamData0
 - fwpsk/FwpsDiscardClonedStreamData0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsDiscardClonedStreamData0
---

# FwpsDiscardClonedStreamData0 function


## -description

The 
  <b>FwpsDiscardClonedStreamData0</b> function frees the memory buffer that is allocated by the 
  <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsclonestreamdata0">FwpsCloneStreamData0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsDiscardClonedStreamData0</b> is a specific version of <b>FwpsDiscardClonedStreamData</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param netBufferListChain 

[in, out]
A pointer to the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure chain that is
     being freed. This will be the same as the 
     <i>netBufferListChain</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsclonestreamdata0">FwpsCloneStreamData0</a> function.

### -param allocateCloneFlags

There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.

### -param dispatchLevel 

[in]
A value that indicates the current IRQL = DISPATCH_LEVEL. A callout driver should set this
     parameter to <b>TRUE</b> only if it is running at IRQL = DISPATCH_LEVEL. Otherwise, a callout driver should set
     this parameter to <b>FALSE</b>.

## -remarks

This function can be called when a cloned 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain is to be discarded
    instead of being reinjected back into the data stream.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsclonestreamdata0">FwpsCloneStreamData0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>