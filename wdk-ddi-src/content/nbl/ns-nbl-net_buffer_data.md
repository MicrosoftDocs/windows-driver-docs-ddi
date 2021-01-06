---
UID: NS:nbl._NET_BUFFER_DATA
title: NET_BUFFER_DATA
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to a NET_BUFFER structure, and it identifies the next NET_BUFFER structure in a list of NET_BUFFER structures.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/nbl.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: NET_BUFFER_DATA, *PNET_BUFFER_DATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - nbl.h
api_name:
 - _NET_BUFFER_DATA
 - PNET_BUFFER_DATA
 - NET_BUFFER_DATA
f1_keywords:
 - _NET_BUFFER_DATA
 - nbl/_NET_BUFFER_DATA
 - PNET_BUFFER_DATA
 - nbl/PNET_BUFFER_DATA
 - NET_BUFFER_DATA
 - nbl/NET_BUFFER_DATA
dev_langs:
 - c++
---

# _NET_BUFFER_DATA structure


## -description

The NET_BUFFER_DATA structure contains information for managing the data buffers that are attached to
  a NET_BUFFER structure, and it identifies the next 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure in a list of NET_BUFFER
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
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a> structure contains a
    NET_BUFFER_DATA structure that defines data for the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure. To access the members of
    NET_BUFFER_DATA, use the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
    NdisRetreatNetBufferDataStart</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
    NdisAdvanceNetBufferDataStart</a> functions, and the following macros:


<a href="/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl-offset">
       NET_BUFFER_CURRENT_MDL_OFFSET</a>


<div class="alert"><b>Note</b>  The C and C++ compilers use different definitions for these macros. Failure to use
    the macros can cause problems when switching compilers.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl">NET_BUFFER_CURRENT_MDL</a>



<a href="/windows-hardware/drivers/network/net-buffer-current-mdl-offset">NET_BUFFER_CURRENT_MDL_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-length">NET_BUFFER_DATA_LENGTH</a>



<a href="/windows-hardware/drivers/network/net-buffer-data-offset">NET_BUFFER_DATA_OFFSET</a>



<a href="/windows-hardware/drivers/network/net-buffer-first-mdl">NET_BUFFER_FIRST_MDL</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_header">NET_BUFFER_HEADER</a>



<a href="/windows-hardware/drivers/network/net-buffer-next-nb">NET_BUFFER_NEXT_NB</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretreatnetbufferdatastart">
   NdisRetreatNetBufferDataStart</a>

