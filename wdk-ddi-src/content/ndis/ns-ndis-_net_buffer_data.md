---
UID: NS:ndis._NET_BUFFER_DATA
title: _NET_BUFFER_DATA (ndis.h)
description: The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to a NET_BUFFER structure, and it identifies the next NET_BUFFER structure in a list of NET_BUFFER structures.
old-location: netvista\net_buffer_data.htm
tech.root: netvista
ms.assetid: d1b5e1c7-5ade-4f54-a5f1-200420964f0e
ms.date: 05/02/2018
ms.keywords: "*PNET_BUFFER_DATA, NET_BUFFER_DATA, NET_BUFFER_DATA structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_DATA, PNET_BUFFER_DATA structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_DATA, ndis/NET_BUFFER_DATA, ndis/PNET_BUFFER_DATA, ndis_netbuf_structures_ref_3e603c77-b97e-4c1f-9fee-e874e741a543.xml, netvista.net_buffer_data"
f1_keywords:
 - "ndis/NET_BUFFER_DATA"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NET_BUFFER_DATA
product:
- Windows
targetos: Windows
req.typenames: NET_BUFFER_DATA, *PNET_BUFFER_DATA
---

# _NET_BUFFER_DATA structure


## -description


The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to
  a NET_BUFFER structure, and it identifies the next 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in a list of NET_BUFFER
  structures.


## -struct-fields




### -field Next

A pointer to the next NET_BUFFER structure in a linked list of NET_BUFFER structures. If this
     structure is the last NET_BUFFER structure in the list, this member is <b>NULL</b>.


### -field CurrentMdl

A pointer to the first MDL that the current driver is using. This member provides an optimization
     that improves performance by skipping over any MDLs that the current driver is not using.


### -field CurrentMdlOffset

The offset, in bytes, to the beginning of the 
     <i>used data space</i> in the MDL that is specified by the 
     <b>CurrentMdl</b> member.


### -field NbDataLength

The length, in bytes, of the used data space in the MDL chain. The maximum length is 0xFFFFFFFF
     bytes.


### -field MdlChain

A pointer to a linked list of MDLs that map a data buffer. The data buffer stores the network
     data.


### -field DataOffset

The offset, in bytes, from the beginning of the MDL chain to the beginning of the network data in
     the MDL chain. This offset is also the size, in bytes, of the 
     <i>unused data space</i>.


## -remarks



The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a> structure contains a
    NET_BUFFER_DATA structure that defines data for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. To access the members of
    NET_BUFFER_DATA, use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
    NdisRetreatNetBufferDataStart</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
    NdisAdvanceNetBufferDataStart</a> functions, and the following macros:


<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl-offset">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>


<div class="alert"><b>Note</b>  The C and C++ compilers use different definitions for these macros. Failure to use
    the macros can cause problems when switching compilers.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-current-mdl-offset">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>
 

 

