---
UID: NF:fwpsk.FwpsNetBufferListAssociateContext1
title: FwpsNetBufferListAssociateContext1 function (fwpsk.h)
description: The FwpsNetBufferListAssociateContext1 function associates the callout driver's context with a network buffer list and configures notification for network buffer list events.Note  FwpsNetBufferListAssociateContext1 is the specific version of FwpsNetBufferListAssociateContext used in Windows 8 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 7, FwpsNetBufferListAssociateContext0 is available.
old-location: netvista\fwpsnetbufferlistassociatecontext1.htm
tech.root: netvista
ms.assetid: 86e9662e-d308-4e3a-98c1-4134186f1bad
ms.date: 05/02/2018
ms.keywords: FwpsNetBufferListAssociateContext1, FwpsNetBufferListAssociateContext1 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListAssociateContext1, netvista.fwpsnetbufferlistassociatecontext1
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsNetBufferListAssociateContext1
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsNetBufferListAssociateContext1 function


## -description


The 
  <b>FwpsNetBufferListAssociateContext1</b> function associates the callout driver's context with a network buffer
  list and configures notification for network buffer list events.<div class="alert"><b>Note</b>  <b>FwpsNetBufferListAssociateContext1</b> is the specific version of <b>FwpsNetBufferListAssociateContext</b> used in Windows 8 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext0">FwpsNetBufferListAssociateContext0</a> is available.</div>
<div> </div>



## -parameters




### -param netBufferList [in, out]

A network buffer list that indicates one or more packets of interest to the callout driver.


### -param layerId [in]

The identifier of the layer in which the context is being associated. When calling this function
     from the NDIS receive path, set this parameter to <b>FWPS_LAYER_NON_WFP</b>.


### -param context [in]

Arbitrary context information set by the callout driver. The filter engine will pass this context
     to the callout driver's      
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn1">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function.


### -param contextTag [in]

A locally unique identifier obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">
     FwpsNetBufferListGetTagForContext0</a> function.


### -param providerGuid

The provider GUID.

### -param deviceObject [in, out]

A pointer to the callout driver's device object.


### -param notifyFn [in]

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn1">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function. The filter engine will send status notifications to this
     function.


### -param flags [in]

This parameter is reserved for future use and is set to zero.


## -returns



The 
     <b>FwpsNetBufferListAssociateContext1</b> function returns one of the following NTSTATUS codes.

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
    <b>FwpsNetBufferListAssociateContext1</b> function associates groups of packets with the callout driver.
    Packets of interest can be tracked for inspection through multiple layers in the stack.

Before calling this function, the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">FwpsNetBufferListGetTagForContext0</a> function must be called to obtain a context tag.

This function is essentially identical to the previous version, 
    
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext0">FwpsNetBufferListAssociateContext0</a>. The only difference is the 
       updated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn1">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function pointed to by the 
       <i>notifyFn</i> parameter.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn1">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext0">FwpsNetBufferListAssociateContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistgettagforcontext0">
   FwpsNetBufferListGetTagForContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistremovecontext0">
   FwpsNetBufferListRemoveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsnetbufferlistretrievecontext0">
   FwpsNetBufferListRetrieveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-packet-tagging">Using Packet Tagging</a>
 

 

