---
UID: NF:fwpsk.FwpsNetBufferListRemoveContext0
title: FwpsNetBufferListRemoveContext0 function
author: windows-driver-content
description: The FwpsNetBufferListRemoveContext0 function removes the context associated with a network buffer list.Note  FwpsNetBufferListRemoveContext0 is a specific version of FwpsNetBufferListRemoveContext.
old-location: netvista\fwpsnetbufferlistremovecontext0.htm
old-project: netvista
ms.assetid: bd3aa1a2-3ff5-47e4-93f6-5cb2022ec630
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.fwpsnetbufferlistremovecontext0, FwpsNetBufferListRemoveContext0, FwpsNetBufferListRemoveContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListRemoveContext0, wfp_ref_2_funct_3_fwps_J-Q_320b667d-7f90-4a71-acff-e5b0b216ea3c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	FwpsNetBufferListRemoveContext0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsNetBufferListRemoveContext0 function


## -description


The 
  <b>FwpsNetBufferListRemoveContext0</b> function removes the context associated with a network buffer
  list.
<div class="alert"><b>Note</b>  <b>FwpsNetBufferListRemoveContext0</b> is a specific version of <b>FwpsNetBufferListRemoveContext</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsNetBufferListRemoveContext0(
  _Inout_opt_ NET_BUFFER_LIST *netBufferList,
  _In_        UINT64          contextTag,
  _In_        UINT32          flags
);
````


## -parameters




### -param netBufferList [in, out, optional]

A network buffer list that indicates one or more packets of interest to the callout driver. This
     parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the function will remove the context from all associated network
     buffer lists.


### -param contextTag [in]

The context tag that was passed in the <i>contextTag</i> parameter to 
     <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a>.


### -param flags [in]

This parameter is reserved for future use and must be zero.


## -returns



The 
     <b>FwpsNetBufferListRemoveContext0</b> function returns one of the following <b>NTSTATUS</b> codes.

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
The context was successfully removed.

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
    <b>FwpsNetBufferListRemoveContext0</b> function asynchronously removes the tagged context associated with a network buffer list.

To associate a context with a network buffer list, call 
    <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">
    FwpsNetBufferListAssociateContext0</a> or <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext1.md">FwpsNetBufferListAssociateContext1</a>.

Usually a callout driver will not need to use this function, because the tagged context
    is removed automatically when the packets move through the stack. This function is provided so that
    a callout driver can stop processing in situations where contexts aren't removed automatically. For example, in the case of an NDIS filter driver, the packets never enter the TCP/IP stack, and the contexts will need to be removed manually by calling <b>FwpsNetBufferListRemoveContext0</b> with the <i>netBufferList</i> parameter set to <b>NULL</b>.




## -see-also

<a href="https://msdn.microsoft.com/a151256b-d69f-4abb-bf68-644f157dfdd7">Using Packet Tagging</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
   FwpsNetBufferListGetTagForContext0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">
   FwpsNetBufferListAssociateContext0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext1.md">FwpsNetBufferListAssociateContext1</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistretrievecontext0.md">
   FwpsNetBufferListRetrieveContext0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListRemoveContext0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

