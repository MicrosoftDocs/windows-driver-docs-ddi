---
UID: NS:ntddndis._NDIS_SRIOV_PF_LUID_INFO
title: _NDIS_SRIOV_PF_LUID_INFO (ntddndis.h)
description: The NDIS_SRIOV_PF_LUID_INFO structure specifies the locally unique identifier (LUID) associated with the network adapter's PCI Express (PCIe) Physical Function (PF).
old-location: netvista\ndis_sriov_pf_luid_info.htm
tech.root: netvista
ms.assetid: 03a83321-8396-4400-a15c-84a3b507702d
ms.date: 05/02/2018
keywords: ["NDIS_SRIOV_PF_LUID_INFO structure"]
ms.keywords: "*PNDIS_SRIOV_PF_LUID_INFO, NDIS_SRIOV_PF_LUID_INFO, NDIS_SRIOV_PF_LUID_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_PF_LUID_INFO, PNDIS_SRIOV_PF_LUID_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_PF_LUID_INFO, netvista.ndis_sriov_pf_luid_info, ntddndis/NDIS_SRIOV_PF_LUID_INFO, ntddndis/PNDIS_SRIOV_PF_LUID_INFO"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: 
targetos: Windows
req.typenames: NDIS_SRIOV_PF_LUID_INFO, *PNDIS_SRIOV_PF_LUID_INFO
f1_keywords:
 - _NDIS_SRIOV_PF_LUID_INFO
 - ntddndis/_NDIS_SRIOV_PF_LUID_INFO
 - PNDIS_SRIOV_PF_LUID_INFO
 - ntddndis/PNDIS_SRIOV_PF_LUID_INFO
 - NDIS_SRIOV_PF_LUID_INFO
 - ntddndis/NDIS_SRIOV_PF_LUID_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_SRIOV_PF_LUID_INFO
---

# _NDIS_SRIOV_PF_LUID_INFO structure


## -description

The <b>NDIS_SRIOV_PF_LUID_INFO</b> structure specifies the locally unique identifier (LUID) associated with the network adapter's PCI Express (PCIe) Physical Function (PF).

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_PF_LUID_INFO</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_PF_LUID_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_PF_LUID_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_PF_LUID_INFO_REVISION_1.

### -field Luid

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a> value that is associated with the PF network adapter. For more information, see the Remarks section.

## -remarks

NDIS generates an LUID for the PF  before NDIS calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>
 function of the miniport driver for the PF. This LUID is valid until NDIS calls the PF miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.

<div class="alert"><b>Note</b>  The value of the <b>Luid</b> member is different from the <b>NetLuid</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>  structure. This structure is passed to the miniport driver through the <i>MiniportInitParameters</i> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.</div>
<div> </div>
An overlying driver queries this LUID through OID query requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-pf-luid">OID_SRIOV_PF_LUID</a>.

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-pf-luid">OID_SRIOV_PF_LUID</a>

