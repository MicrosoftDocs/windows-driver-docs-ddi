---
UID: NF:ndis.NdisUnbindAdapter
title: NdisUnbindAdapter function
author: windows-driver-content
description: Protocol drivers call the NdisUnbindAdapter function to request NDIS to close a binding to an underlying miniport adapter.
old-location: netvista\ndisunbindadapter.htm
old-project: netvista
ms.assetid: 47aacc23-f7d1-4c14-9541-3207debef327
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisUnbindAdapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisUnbindAdapter
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisUnbindAdapter function



## -description
Protocol drivers call the 
  <b>NdisUnbindAdapter</b> function to request NDIS to close a binding to an underlying miniport
  adapter.



## -syntax

````
NDIS_STATUS NdisUnbindAdapter(
  _In_ NDIS_HANDLE NdisBindingHandle
);
````


## -parameters

### -param NdisBindingHandle [in]

A handle that the protocol driver obtained from a call to the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. The handle
     identifies the binding to close.


## -returns
<b>NdisUnbindAdapter</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><b>NdisUnbindAdapter</b> successfully initiated the unbind operation.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><b>NdisUnbindAdapter</b> failed due to insufficient resources.

 


## -remarks
Protocol drivers call 
    <b>NdisUnbindAdapter</b> outside the context of the 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a> or 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> functions.
    NDIS schedules a work item to call the protocol driver's 
    <i>ProtocolUnbindAdapterEx</i> function and returns immediately.

Before the call to 
    <b>NdisUnbindAdapter</b> returns, NDIS can already have closed the binding. Therefore, after the call
    returns, the caller must not assume that the handle it passed to the 
    <i>NdisBindingHandle</i> parameter is still valid.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUnbindAdapter function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

