---
UID: NC:vmbuskernelmodeclientlibapi.FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA
title: FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA (vmbuskernelmodeclientlibapi.h)
description: The VmbChannelPacketGetExternalData function gets any external Memory Descriptor Lists (MDLs) associated with a packet during packet processing.
tech.root: netvista
ms.date: 05/21/2018
keywords: ["FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA callback function"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA
 - vmbuskernelmodeclientlibapi/FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vmbuskernelmodeclientlibapi.h
api_name:
 - FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA
---

# FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketGetExternalData</b>  function gets any external
Memory Descriptor Lists (MDLs) associated with a packet during packet processing.

## -parameters

### -param PacketCompletionContext

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.

### -param Flags

Flags that control how the MDL is mapped. The possible flag values are: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_PACKET_EXTERNAL_DATA_FLAG_READ_ONLY"></a><a id="vmbus_channel_packet_external_data_flag_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_PACKET_EXTERNAL_DATA_FLAG_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
Map MDL as read-only.

</td>
</tr>
</table>

### -param Mdl

 A pointer to the mapped MDL.

## -returns

<b>VmbChannelPacketGetExternalData</b> returns a status code. If this function returns STATUS_PENDING,
the caller must return from the packet processing callback, which will be
called again, possibly at a different IRQL, when the external data is ready.
At this point, a call to this function will succeed and return the external
data.

## -prototype

```cpp
//Declaration

FN_VMB_CHANNEL_PACKET_GET_EXTERNAL_DATA FnVmbChannelPacketGetExternalData; 

// Definition

NTSTATUS FnVmbChannelPacketGetExternalData 
(
	VMBPACKETCOMPLETION PacketCompletionContext
	UINT32 Flags
	PMDL *Mdl
)
{...}

```

## -remarks

Creating an MDL which represents the memory described by this
transaction causes these regions of the virtual machine to be pinned in memory for the remainder of the transaction lifetime.  This is what may cause the function to return STATUS_PENDING, because the regions of the
virtual machine may need to be paged in.


 The MDL returned by this function describes memory that is already
locked in place. Therefore, there is no need to call the
<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a> function.  The MDL will, however, have neither a user-mode virtual
address nor a kernel-mode virtual address.  If the driver that calls this function requires a virtual address to manipulate the memory within the virtual machine, that driver must call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>, or <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>,
and the corresponding unlock function later, like <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>.
An alternative to using a virtual address would be to just pass the MDL on down to a driver which uses it for direct memory access. 

 The driver calling this function is not required to release the MDL.  It becomes invalid upon calling the <a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete">VmbChannelPacketComplete</a> function. The Kernel Mode Client Library (KMCL) later releases it.  

> [!IMPORTANT]
> This function is called through the VMBus Kernel Mode Client Library (KMCL) interface, provided by the Vmbkmcl.sys bus driver. This is a client function accessed from the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md) structure. 
>
> For more information, see the Remarks section of the [**KMCL_CLIENT_INTERFACE_V1**](ns-vmbuskernelmodeclientlibapi-_kmcl_client_interface_v1.md).

## -see-also

<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>



<a href="/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelpacketcomplete">VmbChannelPacketComplete</a>
