---
UID: NC:ndis.IF_SET_OBJECT
title: IF_SET_OBJECT (ndis.h)
description: The ProviderSetObject function sets information that is associated with a network interface.
old-location: netvista\providersetobject.htm
tech.root: netvista
ms.date: 05/02/2018
ms.keywords: IFP_SET_OBJECT, IFP_SET_OBJECT callback function
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IF_SET_OBJECT
 - ndis/IF_SET_OBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - IFP_SET_OBJECT
product:
 - Windows
---

# IF_SET_OBJECT callback function


## -description

The 
  <i>ProviderSetObject</i> function sets information that is associated with a network interface.

## -parameters

### -param ProviderIfContext 

[in]
A handle that identifies the interface provider's context area for the interface. The interface
     provider passed this handle to NDIS in a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
     NdisIfRegisterInterface</a> function.

### -param ObjectId 

[in]
An identifier for the object that is the target of the set request. For a list of object
     identifiers (OIDs) that apply to interface providers, see 
     <a href="/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface
     OIDs</a>.

### -param InputBufferLength 

[in]
The length, in bytes, of the buffer that 
     <i>pInputBuffer</i> points to.

### -param pInputBuffer 

[in]
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
    <a href="/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface OIDs</a>.

Note that there are currently no set OIDs defined.

NDIS calls 
    <i>ProviderSetObject</i> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>
