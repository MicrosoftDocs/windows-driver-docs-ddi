---
UID: NF:ndis.NdisCopyFromNetBufferToNetBuffer
title: NdisCopyFromNetBufferToNetBuffer function (ndis.h)
description: Call the NdisCopyFromNetBufferToNetBuffer function to copy data from a source NET_BUFFER structure to a destination NET_BUFFER structure.
old-location: netvista\ndiscopyfromnetbuffertonetbuffer.htm
tech.root: netvista
ms.assetid: b760e176-3ef7-4495-89c7-ec6b8bb3ed30
ms.date: 05/02/2018
keywords: ["NdisCopyFromNetBufferToNetBuffer function"]
ms.keywords: NdisCopyFromNetBufferToNetBuffer, NdisCopyFromNetBufferToNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisCopyFromNetBufferToNetBuffer, ndis_netbuf_functions_ref_28d10afe-d78a-49ef-8c9c-f90b87d4eeb1.xml, netvista.ndiscopyfromnetbuffertonetbuffer
f1_keywords:
 - "ndis/NdisCopyFromNetBufferToNetBuffer"
 - "NdisCopyFromNetBufferToNetBuffer"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisCopyFromNetBufferToNetBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisCopyFromNetBufferToNetBuffer function


## -description


Call the 
  <b>NdisCopyFromNetBufferToNetBuffer</b> function to copy data from a source 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure to a destination NET_BUFFER
  structure.


## -parameters




### -param Destination [in]

A pointer to a previously allocated destination NET_BUFFER structure.


### -param DestinationOffset [in]

The byte offset within the destination NET_BUFFER structure at which to begin writing the copied
     data. For more information about 
     <i>DestinationOffset</i>, see the following Remarks section.


### -param BytesToCopy [in]

The number of bytes to copy.


### -param Source [in]

A pointer to a previously allocated source NET_BUFFER structure.


### -param SourceOffset [in]

The byte offset within the source NET_BUFFER structure at which to begin copying the data. For
     more information about 
     <i>SourceOffset</i>, see the following Remarks section.


### -param BytesCopied [out]

A pointer to the caller-supplied variable in which this function returns the number of bytes
     actually copied. This number can be less than the value of 
     <i>BytesToCopy</i> if the source runs out of data or the destination runs out of space.


## -returns



<b>NdisCopyFromNetBufferToNetBuffer</b> returns one of the following status values:

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
The copy operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The copy operation failed because of insufficient resources.

</td>
</tr>
</table>
 




## -remarks



The caller of 
    <b>NdisCopyFromNetBufferToNetBuffer</b> allocates the destination 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure and possibly the source
    NET_BUFFER structure as well. The MDLs of the destination NET_BUFFER structure should have enough space
    to receive the data.

If the source NET_BUFFER structure runs out of data or the destination NET_BUFFER structure runs out
    of space before the specified number of bytes has been copied, the copy operation stops. In either case, 
    <b>NdisCopyFromNetBufferToNetBuffer</b> returns the number of bytes successfully copied from the source to
    the destination NET_BUFFER structure.

The caller must ensure that 
    <b>CurrentMdlOffset</b> and 
    <b>CurrentMdl</b> values are correct in the source and destination 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures. NDIS does not change the
    members in the destination NET_BUFFER. The caller must update the 
    <b>DataLength</b>, 
    <b>DataOffset</b>, and 
    <b>CurrentMdlOffset</b> values in the destination NET_BUFFER after 
    <b>NdisCopyFromNetBufferToNetBuffer</b> returns.

NDIS uses the offsets in the 
    <i>DestionationOffset</i> and 
    <i>SourceOffset</i> parameters of 
    <b>NdisCopyFromNetBufferToNetBuffer</b> as offsets from the current data offset. For example, if the 
    <b>CurrentMdlOffset</b> value in the destination NET_BUFFER is 
    <i>x</i>, and 
    <i>DestinationOffset</i> value is 
    <i>y</i>, NDIS copies the data to the destination NET_BUFFER at an 
    <i>x</i>+ 
    <i>y</i> offset in the memory that the 
    <b>CurrentMdl</b> value describes. Similar rules apply to the 
    <b>CurrentMdlOffset</b> in the source NET_BUFFER and the 
    <i>SourceOffset</i> value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>
 

 

