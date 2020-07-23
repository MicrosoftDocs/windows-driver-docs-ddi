---
UID: NF:fwpsk.FwpsNetBufferListAssociateContext0
title: FwpsNetBufferListAssociateContext0 function (fwpsk.h)
description: The FwpsNetBufferListAssociateContext0 function associates the callout driver's context with a network buffer list and configures notification for network buffer list events.Note  FwpsNetBufferListAssociateContext0 is the specific version of FwpsNetBufferListAssociateContext used in Windows 7 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 8, FwpsNetBufferListAssociateContext1 is available.
old-location: netvista\fwpsnetbufferlistassociatecontext0.htm
tech.root: netvista
ms.assetid: 31135396-303b-4b94-8616-a4b7be207fa1
ms.date: 05/02/2018
keywords: ["FwpsNetBufferListAssociateContext0 function"]
ms.keywords: FwpsNetBufferListAssociateContext0, FwpsNetBufferListAssociateContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListAssociateContext0, netvista.fwpsnetbufferlistassociatecontext0, wfp_ref_2_funct_3_fwps_J-Q_f30e27fe-3146-4393-b967-fdb7bbfd6370.xml
f1_keywords:
 - "fwpsk/FwpsNetBufferListAssociateContext0"
 - "FwpsNetBufferListAssociateContext0"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsNetBufferListAssociateContext0
targetos: Windows
req.typenames: 
---

# FwpsNetBufferListAssociateContext0 function


## -description


The 
  <b>FwpsNetBufferListAssociateContext0</b> function associates the callout driver's context with a network buffer
  list and configures notification for network buffer list events.
<div class="alert"><b>Note</b>  <b>FwpsNetBufferListAssociateContext0</b> is the specific version of <b>FwpsNetBufferListAssociateContext</b> used in Windows 7 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a> is available.</div><div> </div>

## -parameters




### -param netBufferList [in, out]

A network buffer list that indicates one or more packets of interest to the callout driver.


### -param layerId [in]

The identifier of the layer in which the context is being associated. When calling this function
     from the NDIS receive path, set this parameter to FWPS_LAYER_NON_WFP.


### -param context [in]

Arbitrary context information set by the callout driver. The filter engine will pass this context
     to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>.


### -param contextTag [in]

A locally unique identifier obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">
     FwpsNetBufferListGetTagForContext0</a> function.


### -param providerGuid

The provider GUID.

### -param deviceObject [in, out]

A pointer to the callout driver's device object.


### -param notifyFn [in]

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">
     FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> function. The filter engine will send status notifications to this
     function.


### -param flags [in]

This parameter is reserved for future use and is set to zero.


## -returns



The 
     <b>FwpsNetBufferListAssociateContext0</b> function returns one of the following NTSTATUS codes.

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
The association was successful.

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



The 
    <b>FwpsNetBufferListAssociateContext0</b> function associates groups of packets with the callout driver.
    Packets of interest can be tracked for inspection through multiple layers in the stack.

Before calling this function, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">FwpsNetBufferListGetTagForContext0</a> function must be called to obtain a context tag.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">
   FwpsNetBufferListGetTagForContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistremovecontext0">
   FwpsNetBufferListRemoveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistretrievecontext0">
   FwpsNetBufferListRetrieveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-packet-tagging">Using Packet Tagging</a>
 

 

