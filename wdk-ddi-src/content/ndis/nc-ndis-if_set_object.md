---
UID: NC:ndis.IF_SET_OBJECT
title: IF_SET_OBJECT
author: windows-driver-content
description: The ProviderSetObject function sets information that is associated with a network interface.
old-location: netvista\providersetobject.htm
old-project: netvista
ms.assetid: e5dcb46e-5a8a-45b7-b6aa-150a9cec0155
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*IFP_SET_OBJECT, *IFP_SET_OBJECT callback function [Network Drivers Starting with Windows Vista], IF_SET_OBJECT, ProviderSetObject, ProviderSetObject callback function [Network Drivers Starting with Windows Vista], ndis/ProviderSetObject, net_if_provider_functions_ref_8da505c4-dd64-43c8-a6a4-ad13cc4b18d0.xml, netvista.providersetobject"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	*IFP_SET_OBJECT
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# IF_SET_OBJECT callback


## -description


The 
  <i>ProviderSetObject</i> function sets information that is associated with a network interface.


## -parameters




### -param ProviderIfContext [in]

A handle that identifies the interface provider's context area for the interface. The interface
     provider passed this handle to NDIS in a call to the 
     <a href="https://msdn.microsoft.com/d0b0ada7-afb1-4cb7-ada6-7c5c7abe7d19">
     NdisIfRegisterInterface</a> function.


### -param ObjectId [in]

An identifier for the object that is the target of the set request. For a list of object
     identifiers (OIDs) that apply to interface providers, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface
     OIDs</a>.


### -param InputBufferLength [in]

The length, in bytes, of the buffer that 
     <i>pInputBuffer</i> points to.


### -param pInputBuffer [in]

A pointer to an input buffer that specifies the information that the interface provider should use
     to set the object data.


## -returns



<i>ProviderSetObject</i> returns one of the following status values:

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
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The call failed because some of the input parameters were invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_Xxx</b></dt>
</dl>
</td>
<td width="60%">
The call failed for some other reason. This function can propagate error codes from the
       functions that it calls or generate an appropriate error code.

</td>
</tr>
</table>
 




## -remarks



NDIS calls a network interface provider's 
    <i>ProviderSetObject</i> function to set information that is associated with an interface that the
    provider registered. For a list of OIDs that apply to interface providers, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface OIDs</a>.

Note that there are currently no set OIDs defined.

NDIS calls 
    <i>ProviderSetObject</i> at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562715">NdisIfRegisterInterface</a>
 

 

