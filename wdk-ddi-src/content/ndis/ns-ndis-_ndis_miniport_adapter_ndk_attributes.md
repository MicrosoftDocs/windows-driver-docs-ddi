---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES (ndis.h)
description: The NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure specifies the NDK-capabilities of a miniport adapter. This structure is used in the NDKAttributes member of the NDIS_MINIPORT_ADAPTER_ATTRIBUTES union.
old-location: netvista\ndis_miniport_adapter_ndk_attributes.htm
tech.root: netvista
ms.assetid: 615A190E-D8F5-4E84-A475-FFF38077BC09
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, ndis/NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, netvista.ndis_miniport_adapter_ndk_attributes"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.typenames: NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
f1_keywords:
 - _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
 - ndis/_NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
 - PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
 - ndis/PNDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
 - NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
 - ndis/NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES structure


## -description

The <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure specifies the NDK-capabilities of a miniport adapter. This structure is used in the <b>NDKAttributes</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union.

## -struct-fields

### -field Header

A <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure. 

Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_MINIPORT_ADAPTER_NDK_ATTRIBUTES_REVISION_1</b>.</li>
</ul>

### -field Enabled

If the miniport adapter's NDK functionality is enabled, this member is <b>TRUE</b>. Otherwise, it is <b>FALSE</b>.

### -field NdkCapabilities

A pointer to an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a> structure that specifies the capabilities of an NDK adapter.

## -remarks

An NDK-capable adapter must indicate its NDK capabilities in its <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function, even if its NDK functionality is currently disabled.

To report its NDK capabilities, the miniport adapter stores an  <b>NDIS_MINIPORT_ADAPTER_NDK_ATTRIBUTES</b> structure in the <b>NDKAttributes</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a> union and passes  the <b>NDIS_MINIPORT_ADAPTER_ATTRIBUTES</b> union  to the <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a> function. For more information, see <a href="/windows-hardware/drivers/network/initializing-an-ndk-miniport-adapter">Initializing an NDK Miniport Adapter</a>.

## -see-also

<a href="/windows-hardware/drivers/network/initializing-an-ndk-miniport-adapter">Initializing an NDK Miniport Adapter</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_attributes">NDIS_MINIPORT_ADAPTER_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>