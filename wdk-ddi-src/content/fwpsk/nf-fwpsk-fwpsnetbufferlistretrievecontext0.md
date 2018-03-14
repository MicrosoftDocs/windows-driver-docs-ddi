---
UID: NF:fwpsk.FwpsNetBufferListRetrieveContext0
title: FwpsNetBufferListRetrieveContext0 function
author: windows-driver-content
description: The FwpsNetBufferListRetrieveContext0 function retrieves the context associated with a network buffer list that was tagged in another layer.Note  FwpsNetBufferListRetrieveContext0 is a specific version of FwpsNetBufferListRetrieveContext.
old-location: netvista\fwpsnetbufferlistretrievecontext0.htm
old-project: netvista
ms.assetid: 482cec75-8a21-4988-b869-639d019f9460
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FwpsNetBufferListRetrieveContext0, FwpsNetBufferListRetrieveContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListRetrieveContext0, netvista.fwpsnetbufferlistretrievecontext0, wfp_ref_2_funct_3_fwps_J-Q_63312511-d342-4705-86d9-844c59f42fe3.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsNetBufferListRetrieveContext0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsNetBufferListRetrieveContext0 function


## -description


The 
  <b>FwpsNetBufferListRetrieveContext0</b> function retrieves the context associated with a network buffer
  list that was tagged in another layer.
<div class="alert"><b>Note</b>  <b>FwpsNetBufferListRetrieveContext0</b> is a specific version of <b>FwpsNetBufferListRetrieveContext</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsNetBufferListRetrieveContext0(
  _Inout_ NET_BUFFER_LIST *netBufferList,
  _In_    UINT64          contextTag,
  _In_    BOOLEAN         removeContext,
  _In_    UINT32          flags,
  _Out_   UINT64          *context
);
````


## -parameters




### -param netBufferList [in, out]

A network buffer list that indicates one or more packets of interest to the callout driver. If 
     <i>removeContext</i> is set, the network buffer list returned will have the context removed.


### -param contextTag [in]

A locally unique identifier obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
     FwpsNetBufferListGetTagForContext0</a> function. This is the context tag used in the initial call to 
     <a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">FwpsNetBufferListAssociateContext0</a>.


### -param removeContext [in]

If set, 
     <b>FwpsNetBufferListRetrieveContext0</b> will remove the context association in addition to retrieving
     the context.


### -param flags [in]

This parameter is reserved for future use and is set to zero.


### -param context [out]

The context assigned to the packet by the callout driver in the initial call to 
     <b>FwpsNetBufferListAssociateContext0</b>.


## -returns



The 
     <b>FwpsNetBufferListRetrieveContext0</b> function returns one of the following NTSTATUS codes.

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
    <b>FwpsNetBufferListRetrieveContext0</b> function retrieves a network buffer list that was tagged in
    another layer.

You can also use this function to remove the context association by setting the 
    <i>removeContext</i> parameter.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
   FwpsNetBufferListGetTagForContext0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">
   FwpsNetBufferListAssociateContext0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistremovecontext0.md">
   FwpsNetBufferListRemoveContext0</a>



 

 


