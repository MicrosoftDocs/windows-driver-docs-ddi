---
UID: NF:fwpsk.FwpsNetBufferListRetrieveContext0
title: FwpsNetBufferListRetrieveContext0 function
author: windows-driver-content
description: The FwpsNetBufferListRetrieveContext0 function retrieves the context associated with a network buffer list that was tagged in another layer.Note  FwpsNetBufferListRetrieveContext0 is a specific version of FwpsNetBufferListRetrieveContext.
old-location: netvista\fwpsnetbufferlistretrievecontext0.htm
old-project: netvista
ms.assetid: 482cec75-8a21-4988-b869-639d019f9460
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpsNetBufferListRetrieveContext0
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
req.alt-api: FwpsNetBufferListRetrieveContext0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
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
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsNetBufferListRetrieveContext0 function



## -description
The 
  <b>FwpsNetBufferListRetrieveContext0</b> function retrieves the context associated with a network buffer
  list that was tagged in another layer.



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
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The association was successful.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
The 
    <b>FwpsNetBufferListRetrieveContext0</b> function retrieves a network buffer list that was tagged in
    another layer.

You can also use this function to remove the context association by setting the 
    <i>removeContext</i> parameter.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistassociatecontext0.md">
   FwpsNetBufferListAssociateContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistgettagforcontext0.md">
   FwpsNetBufferListGetTagForContext0</a>
</dt>
<dt>
<a href="..\fwpsk\nf-fwpsk-fwpsnetbufferlistremovecontext0.md">
   FwpsNetBufferListRemoveContext0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsNetBufferListRetrieveContext0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

