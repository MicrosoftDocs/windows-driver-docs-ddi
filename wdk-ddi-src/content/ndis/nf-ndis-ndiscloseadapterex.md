---
UID: NF:ndis.NdisCloseAdapterEx
title: NdisCloseAdapterEx function
author: windows-driver-content
description: A protocol driver calls the NdisCloseAdapterEx function to release the binding and the resources that were allocated when the driver called the NdisOpenAdapterEx function.
old-location: netvista\ndiscloseadapterex.htm
tech.root: netvista
ms.assetid: 8e3c6373-e39d-4f9b-b874-e3a9c93791b9
ms.date: 05/02/2018
ms.keywords: NdisCloseAdapterEx, NdisCloseAdapterEx function [Network Drivers Starting with Windows Vista], ndis/NdisCloseAdapterEx, netvista.ndiscloseadapterex, protocol_ndis_functions_ref_f349b273-d8c6-4711-af43-59646c41536c.xml
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisCloseAdapterEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCloseAdapterEx function


## -description


A protocol driver calls the 
  <b>NdisCloseAdapterEx</b> function to release the binding and the resources that were allocated when the
  driver called the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <b>NdisOpenAdapterEx</b>. This handle identifies the binding that NDIS should close.


## -returns



<b>NdisCloseAdapterEx</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisCloseAdapterEx</b> successfully closed the binding to the underlying miniport adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisCloseAdapterEx</b> did not complete the close operation and the operation will be completed
       asynchronously. NDIS calls the protocol driver's 
       <a href="https://msdn.microsoft.com/62cc047a-bc91-4e1e-817e-7fd509d4d90e">
       ProtocolCloseAdapterCompleteEx</a> function when the operation is complete.

</td>
</tr>
</table>
 




## -remarks



A protocol driver typically calls 
    <b>NdisCloseAdapterEx</b> from its 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function. The driver can also call 
    <b>NdisCloseAdapterEx</b> from its 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function.
    For example, if the driver failed to set an OID value after it called 
    <b>NdisOpenAdapterEx</b>, it can call 
    <b>NdisCloseAdapterEx</b> from its 
    <i>ProtocolBindAdapterEx</i> function.

If a protocol driver must close a miniport adapter outside the context of 
    <i>ProtocolUnbindAdapterEx</i> or 
    <i>ProtocolBindAdapterEx</i>, it must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564630">NdisUnbindAdapter</a> function.

Protocol drivers should wait for all send requests and OID requests that they originated to complete
    before calling 
    <b>NdisCloseAdapterEx</b>.

As soon as the driver calls 
    <b>NdisCloseAdapterEx</b>, the handle obtained from the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function at the 
    <i>NdisBindingHandle</i> parameter becomes invalid.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564630">NdisUnbindAdapter</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/62cc047a-bc91-4e1e-817e-7fd509d4d90e">
   ProtocolCloseAdapterCompleteEx</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

