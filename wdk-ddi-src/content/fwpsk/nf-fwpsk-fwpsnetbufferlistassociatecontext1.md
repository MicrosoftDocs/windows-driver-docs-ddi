---
UID: NF:fwpsk.FwpsNetBufferListAssociateContext1
title: FwpsNetBufferListAssociateContext1 function
author: windows-driver-content
description: The FwpsNetBufferListAssociateContext1 function associates the callout driver's context with a network buffer list and configures notification for network buffer list events.Note  FwpsNetBufferListAssociateContext1 is the specific version of FwpsNetBufferListAssociateContext used in Windows 8 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 7, FwpsNetBufferListAssociateContext0 is available.
old-location: netvista\fwpsnetbufferlistassociatecontext1.htm
old-project: netvista
ms.assetid: 86e9662e-d308-4e3a-98c1-4134186f1bad
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.fwpsnetbufferlistassociatecontext1, fwpsk/FwpsNetBufferListAssociateContext1, FwpsNetBufferListAssociateContext1, FwpsNetBufferListAssociateContext1 function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsNetBufferListAssociateContext1
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsNetBufferListAssociateContext1 function


## -description


The 
  <b>FwpsNetBufferListAssociateContext1</b> function associates the callout driver's context with a network buffer
  list and configures notification for network buffer list events.<div class="alert"><b>Note</b>  <b>FwpsNetBufferListAssociateContext1</b> is the specific version of <b>FwpsNetBufferListAssociateContext</b> used in Windows 8 and later. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a> is available.</div>
<div> </div>



## -syntax


````
NTSTATUS NTAPI FwpsNetBufferListAssociateContext1(
  _Inout_ NET_BUFFER_LIST                 *netBufferList,
  _In_    UINT16                          layerId,
  _In_    UINT64                          context,
  _In_    UINT64                          contextTag,
  _In_    GUID                            *providerGUID,
  _Inout_ void                            *deviceObject,
  _In_    FWPS_NET_BUFFER_LIST_NOTIFY_FN1 notifyFn,
  _In_    UINT32                          flags
);
````


## -parameters




### -param netBufferList [in, out]

A network buffer list that indicates one or more packets of interest to the callout driver.


### -param layerId [in]

The identifier of the layer in which the context is being associated. When calling this function
     from the NDIS receive path, set this parameter to <b>FWPS_LAYER_NON_WFP</b>.


### -param context [in]

Arbitrary context information set by the callout driver. The filter engine will pass this context
     to the callout driver's 
     
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn1.md">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function.


### -param contextTag [in]

A locally unique identifier obtained by calling the 
     <mshelp:link keywords="netvista.fwpsnetbufferlistgettagforcontext0" tabindex="0"><b>
     FwpsNetBufferListGetTagForContext0</b></mshelp:link> function.


### -param providerGuid

TBD


### -param deviceObject [in, out]

A pointer to the callout driver's device object.


### -param notifyFn [in]

A pointer to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn1.md">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function. The filter engine will send status notifications to this
     function.


### -param flags [in]

This parameter is reserved for future use and is set to zero.


#### - providerGUID [in]

The provider GUID.


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
    <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">FwpsNetBufferListGetTagForContext0</a> function must be called to obtain a context tag.

This function is essentially identical to the previous version, 
    
  <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a>. The only difference is the 
       updated <a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn1.md">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a> function pointed to by the 
       <i>notifyFn</i> parameter.



## -see-also

<a href="https://msdn.microsoft.com/a151256b-d69f-4abb-bf68-644f157dfdd7">Using Packet Tagging</a>

<mshelp:link keywords="netvista.fwpsnetbufferlistretrievecontext0" tabindex="0"><b>
   FwpsNetBufferListRetrieveContext0</b></mshelp:link>

<mshelp:link keywords="netvista.fwpsnetbufferlistgettagforcontext0" tabindex="0"><b>
   FwpsNetBufferListGetTagForContext0</b></mshelp:link>

<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<mshelp:link keywords="netvista.fwpsnetbufferlistremovecontext0" tabindex="0"><b>
   FwpsNetBufferListRemoveContext0</b></mshelp:link>

<a href="..\fwpsk\nc-fwpsk-fwps_net_buffer_list_notify_fn1.md">FWPS_NET_BUFFER_LIST_NOTIFY_FN1</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListAssociateContext1 function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

