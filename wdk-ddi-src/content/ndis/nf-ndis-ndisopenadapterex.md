---
UID: NF:ndis.NdisOpenAdapterEx
title: NdisOpenAdapterEx function
author: windows-driver-content
description: A protocol driver calls the NdisOpenAdapterEx function from its ProtocolBindAdapterEx function to set up a binding between the protocol driver and an underlying driver.
old-location: netvista\ndisopenadapterex.htm
tech.root: netvista
ms.assetid: 2dc356e6-a2ef-4b43-abe5-7c5058c15cf5
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisOpenAdapterEx, NdisOpenAdapterEx function [Network Drivers Starting with Windows Vista], ndis/NdisOpenAdapterEx, netvista.ndisopenadapterex, protocol_ndis_functions_ref_7ea04244-bfbb-460d-86f3-35e908850c6a.xml
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
-	NdisOpenAdapterEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOpenAdapterEx function


## -description


A protocol driver calls the
  <b>NdisOpenAdapterEx</b> function from its 
  <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function to
  set up a binding between the protocol driver and an underlying driver.


## -parameters




### -param NdisProtocolHandle [in]

The handle returned by the 
     <a href="https://msdn.microsoft.com/b48571eb-13a2-4541-80ac-c8d31f378d37">
     NdisRegisterProtocolDriver</a> function.


### -param ProtocolBindingContext [in]

The handle for a caller-supplied context area in which the protocol driver maintains state
     information for this binding.


### -param OpenParameters [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566734">NDIS_OPEN_PARAMETERS</a> structure that is
     set up by the caller.


### -param BindContext [in]

The handle that identifies the NDIS context area for the bind operation. NDIS passed this handle
     to the 
     <i>BindContext</i> parameter of the 
     <i>ProtocolBindAdapterEx</i> function.


### -param NdisBindingHandle [out]

A pointer to a caller-supplied variable. NDIS writes a handle at 
     <i>NdisBindingHandle</i> that identifies the binding between the caller and the miniport adapter
     specified in the 
     <b>AdapterName</b> member at 
     <i>OpenParameters</i> . The caller uses this handle in subsequent calls to 
     <b>Ndis<i>Xxx</i></b> functions.


## -returns



<b>NdisOpenAdapterEx</b> returns one of the following status values:

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
<b>NdisOpenAdapterEx</b> successfully completed the open operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenAdapterEx</b> did not complete the open operation. NDIS later calls the protocol driver's 
       <a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
       ProtocolOpenAdapterCompleteEx</a> function to complete the open operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenAdapterEx</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_ADAPTER_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenAdapterEx</b> failed because a miniport adapter specified in the 
       <b>AdapterName</b> member at 
       <i>OpenParameters</i> could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_UNSUPPORTED_MEDIA</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenAdapterEx</b> failed because the array specified in the 
       <b>MediumArray</b> member at 
       <i>OpenParameters</i> did not include a medium type that NDIS or the underlying driver supports.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisOpenAdapterEx</b> failed for reasons other than those in the preceding list.

</td>
</tr>
</table>
 




## -remarks



A protocol driver must call 
    <b>NdisOpenAdapterEx</b> from its 
    <a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a> function.
    NDIS fails any attempt to call 
    <b>NdisOpenAdapterEx</b> outside the context of 
    <i>ProtocolBindAdapterEx</i>.

If 
    <b>NdisOpenAdapterEx</b> returns NDIS_STATUS_PENDING, the caller must not use the values at 
    <i>NdisBindingHandle</i> and the 
    <b>SelectedMediumIndex</b> member at 
    <i>OpenParameters</i> until NDIS calls the 
    <a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
    ProtocolOpenAdapterCompleteEx</a> function.

The string at 
    <b>AdapterName</b> must remain valid only until 
    <b>NdisOpenAdapterEx</b> returns. Therefore, in the case that 
    <b>NdisOpenAdapterEx</b> returns NDIS_STATUS_PENDING, the driver is not required to continue to retain
    this string after 
    <b>NdisOpenAdapterEx</b> returns.

After the open operation completes successfully, the caller can use the value that NDIS returned in
    the 
    <i>NdisBindingHandle</i> in subsequent calls to 
    <b>Ndis<i>Xxx</i></b> functions. The caller can use the 
    <b>SelectedMediumIndex</b> member of the 
    <i>OpenParameters</i> parameter to determine how it should interact with the underlying driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566734">NDIS_OPEN_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/1958722e-012e-4110-a82c-751744bcf9b5">ProtocolBindAdapterEx</a>



<a href="https://msdn.microsoft.com/59d18822-8ce2-4506-90d7-9f1cdc7a9e10">
   ProtocolOpenAdapterCompleteEx</a>
 

 

