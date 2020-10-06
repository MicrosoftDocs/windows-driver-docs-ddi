---
UID: NS:ndis._NDIS_PD_OPEN_PROVIDER_PARAMETERS
title: _NDIS_PD_OPEN_PROVIDER_PARAMETERS (ndis.h)
description: This structure is used as a buffer for parameters in the OID_PD_OPEN_PROVIDER OID.
old-location: netvista\ndis_pd_open_provider_parameters.htm
tech.root: netvista
ms.assetid: 38612533-DC8A-4D46-9C95-9F16BD9C27AB
ms.date: 05/02/2018
keywords: ["NDIS_PD_OPEN_PROVIDER_PARAMETERS structure"]
ms.keywords: NDIS_PD_OPEN_PROVIDER_PARAMETERS, NDIS_PD_OPEN_PROVIDER_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_PD_OPEN_PROVIDER_PARAMETERS, ndis/NDIS_PD_OPEN_PROVIDER_PARAMETERS, netvista.ndis_pd_open_provider_parameters
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: 
targetos: Windows
req.typenames: NDIS_PD_OPEN_PROVIDER_PARAMETERS
f1_keywords:
 - _NDIS_PD_OPEN_PROVIDER_PARAMETERS
 - ndis/_NDIS_PD_OPEN_PROVIDER_PARAMETERS
 - NDIS_PD_OPEN_PROVIDER_PARAMETERS
 - ndis/NDIS_PD_OPEN_PROVIDER_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ndis.h
api_name:
 - NDIS_PD_OPEN_PROVIDER_PARAMETERS
---

# _NDIS_PD_OPEN_PROVIDER_PARAMETERS structure


## -description

This structure is used as a buffer for parameters in the <a href="/windows-hardware/drivers/network/oid-pd-open-provider">OID_PD_OPEN_PROVIDER</a> OID.

## -struct-fields

### -field Header

The <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_OPEN_PROVIDER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_OPEN_PROVIDER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_OPEN_PROVIDER_PARAMETERS_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be 0.

### -field ProviderHandle

A provider handle that identifies the PD-capable miniport driver's provider object.

### -field ProviderDispatch

See <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_pd_provider_dispatch">NDIS_PD_PROVIDER_DISPATCH</a>.

## -remarks

This structure must be aligned on an 8-byte boundary.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>