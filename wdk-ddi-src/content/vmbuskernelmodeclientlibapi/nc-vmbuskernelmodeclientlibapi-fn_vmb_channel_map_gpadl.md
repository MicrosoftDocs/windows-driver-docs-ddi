---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_MAP_GPADL
title: FN_VMB_CHANNEL_MAP_GPADL (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelMapGpadl function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number.
tech.root: netvista
ms.assetid: b71b9fbe-ab6c-41a6-8288-b98ebfc240dc
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_MAP_GPADL callback function"]
f1_keywords:
 - "vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_MAP_GPADL"
 - "FN_VMB_CHANNEL_MAP_GPADL"
req.header: vmbuskernelmodeclientlibapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- vmbuskernelmodeclientlibapi.h
api_name: 
- FN_VMB_CHANNEL_MAP_GPADL
targetos: Windows
ms.custom: RS5
---

# FN_VMB_CHANNEL_MAP_GPADL callback function

## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelMapGpadl</b>  function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number. 

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_MAP_GPADL FnVmbChannelMapGpadl; 

// Definition

NTSTATUS FnVmbChannelMapGpadl 
(
	VMBCHANNEL Channel
	UINT32 Flags
	UINT32 GpadlHandle
	PMDL *Mdl
)
{...}

```

## -parameters

### -param Channel

A handle for a channel. 

### -param Flags

Flags.  The possible flag values are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY"></a><a id="vmbus_channel_gpadl_flag_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
Map with read-only access. 

</td>
</tr>
</table>
 

If
this flag value is not set, the function tries to map the GPADL for write access. If the GPADL was not
created with write access, this mapping attempt fails. The
caller is not prevented from writing to the buffer if this flag is set. This scheme is used to improve the performance of live migration
and snapshotting.

### -param GpadlHandle

The GPADL handle of the GPADL to map.

### -param Mdl: 

 A pointer to a MDL describing the client buffer. This
buffer is only mapped into physical address space. The caller must take
additional steps to map it into virtual address space.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or an appropriate NTSTATUS error code otherwise.

## -remarks

The GPADL must have been pre-established by the client, for instance, by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrombuffer">VmbChannelCreateGpadlFromBuffer</a> function.  

Only a single mapping may exist for any given GPADL at a time.  

You must pair calls to this
function with calls to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelunmapgpadl">VmbChannelUnmapGpadl</a> function.

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a server-only function accessed from the [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md) structure. 
>
> For more information, see the Remarks section of [**KMCL_SERVER_ONLY_METHODS**](ns-vmbuskernelmodeclientlibapi-_kmcl_server_only_methods.md).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelcreategpadlfrombuffer">VmbChannelCreateGpadlFromBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelunmapgpadl">VmbChannelUnmapGpadl</a>
