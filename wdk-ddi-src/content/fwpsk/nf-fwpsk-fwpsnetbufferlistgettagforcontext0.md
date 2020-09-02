---
UID: NF:fwpsk.FwpsNetBufferListGetTagForContext0
title: FwpsNetBufferListGetTagForContext0 function (fwpsk.h)
description: The FwpsNetBufferListGetTagForContext0 function gets a locally unique context tag that can be used to associate packets with the callout driver.Note  FwpsNetBufferListGetTagForContext0 is a specific version of FwpsNetBufferListGetTagForContext.
old-location: netvista\fwpsnetbufferlistgettagforcontext0.htm
tech.root: netvista
ms.assetid: f4b9b6ab-2251-4b8a-baf5-16c845a1a4db
ms.date: 05/02/2018
keywords: ["FwpsNetBufferListGetTagForContext0 function"]
ms.keywords: FwpsNetBufferListGetTagForContext0, FwpsNetBufferListGetTagForContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListGetTagForContext0, netvista.fwpsnetbufferlistgettagforcontext0, wfp_ref_2_funct_3_fwps_J-Q_f81dda7b-70fb-42ae-8641-c9bb2a9e7982.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 7.
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
 - FwpsNetBufferListGetTagForContext0
 - fwpsk/FwpsNetBufferListGetTagForContext0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsNetBufferListGetTagForContext0
---

# FwpsNetBufferListGetTagForContext0 function


## -description

The <b>FwpsNetBufferListGetTagForContext0</b> function gets a locally unique context tag that can be used to
  associate packets with the callout driver.
<div class="alert"><b>Note</b>  <b>FwpsNetBufferListGetTagForContext0</b> is a specific version of <b>FwpsNetBufferListGetTagForContext</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -returns

The 
     <b>FwpsNetBufferListGetTagForContext0</b> function returns a locally unique identifier.

## -remarks

The 
    <b>FwpsNetBufferListGetTagForContext0</b> function must be called before calling 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext0">FwpsNetBufferListAssociateContext0</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext0">
   FwpsNetBufferListAssociateContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistremovecontext0">
   FwpsNetBufferListRemoveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistretrievecontext0">
   FwpsNetBufferListRetrieveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-packet-tagging">Using Packet Tagging</a>

