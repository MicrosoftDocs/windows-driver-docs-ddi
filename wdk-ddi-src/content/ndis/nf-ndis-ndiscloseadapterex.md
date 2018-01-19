---
UID: NF:ndis.NdisCloseAdapterEx
title: NdisCloseAdapterEx function
author: windows-driver-content
description: A protocol driver calls the NdisCloseAdapterEx function to release the binding and the resources that were allocated when the driver called the NdisOpenAdapterEx function.
old-location: netvista\ndiscloseadapterex.htm
old-project: netvista
ms.assetid: 8e3c6373-e39d-4f9b-b874-e3a9c93791b9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisCloseAdapterEx
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
req.alt-api: NdisCloseAdapterEx
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
req.irql: PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCloseAdapterEx function



## -description
A protocol driver calls the 
  <b>NdisCloseAdapterEx</b> function to release the binding and the resources that were allocated when the
  driver called the 
  <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.



## -syntax

````
NDIS_STATUS NdisCloseAdapterEx(
  _In_ NDIS_HANDLE NdisBindingHandle
);
````


## -parameters

### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <b>NdisOpenAdapterEx</b>. This handle identifies the binding that NDIS should close.


## -returns
<b>NdisCloseAdapterEx</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><b>NdisCloseAdapterEx</b> successfully closed the binding to the underlying miniport adapter.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><b>NdisCloseAdapterEx</b> did not complete the close operation and the operation will be completed
       asynchronously. NDIS calls the protocol driver's 
       <a href="..\ndis\nc-ndis-protocol_close_adapter_complete_ex.md">
       ProtocolCloseAdapterCompleteEx</a> function when the operation is complete.

 


## -remarks
A protocol driver typically calls 
    <b>NdisCloseAdapterEx</b> from its 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function. The driver can also call 
    <b>NdisCloseAdapterEx</b> from its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function.
    For example, if the driver failed to set an OID value after it called 
    <b>NdisOpenAdapterEx</b>, it can call 
    <b>NdisCloseAdapterEx</b> from its 
    <i>ProtocolBindAdapterEx</i> function.

If a protocol driver must close a miniport adapter outside the context of 
    <i>ProtocolUnbindAdapterEx</i> or 
    <i>ProtocolBindAdapterEx</i>, it must call the 
    <a href="..\ndis\nf-ndis-ndisunbindadapter.md">NdisUnbindAdapter</a> function.

Protocol drivers should wait for all send requests and OID requests that they originated to complete
    before calling 
    <b>NdisCloseAdapterEx</b>.

As soon as the driver calls 
    <b>NdisCloseAdapterEx</b>, the handle obtained from the 
    <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function at the 
    <i>NdisBindingHandle</i> parameter becomes invalid.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisunbindadapter.md">NdisUnbindAdapter</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_close_adapter_complete_ex.md">
   ProtocolCloseAdapterCompleteEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCloseAdapterEx function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

