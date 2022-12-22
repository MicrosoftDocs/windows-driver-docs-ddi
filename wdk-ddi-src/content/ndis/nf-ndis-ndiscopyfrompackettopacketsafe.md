---
UID: NF:ndis.NdisCopyFromPacketToPacketSafe
tech.root: 
title: NdisCopyFromPacketToPacketSafe
ms.date: 
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ndis.h
req.idl: 
req.include-header: Ndis.h
req.irql: <= DISPATCH_LEVEL>
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Kernel32.dll
 - ndis.h
api_name:
 - NdisCopyFromPacketToPacketSafe
f1_keywords:
 - NdisCopyFromPacketToPacketSafe
 - ndis/NdisCopyFromPacketToPacketSafe
dev_langs:
 - c++
helpviewer_keywords:
 - NdisCopyFromPacketToPacketSafe
---

# NdisCopyFromPacketToPacket function



## -description
**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisCopyFromPacketToPacket** copies a specified range of data from one packet to another.

## -parameters

### -param Destination [in]

Pointer to the destination packet descriptor.

### -param DestinationOffset [in]

Specifies the byte offset within the destination packet at which to begin writing the copied data.

### -param BytesToCopy [in]

Specifies the number of bytes to copy.

### -param Source [in]

Pointer to the source packet descriptor.

### -param SourceOffset [in]

Specifies the byte offset within the source packet at which to begin copying the data.

### -param BytesCopied [out]

Pointer to the caller-supplied variable in which this function returns the number of bytes actually copied. This number can be less than the value of *BytesToCopy* if the source packet runs out of data or the destination packet runs out of space.

### -param Priority

## -remarks

Return value: None

Drivers should call [**NdisCopyFromPacketToPacketSafe**](ff551071\(v=vs.85\).md) instead of **NdisCopyFromPacketToPacket**. NDIS 5.1 miniport drivers must call **NdisCopyFromPacketToPacketSafe** instead of **NdisCopyFromPacketToPacket**. Unlike **NdisCopyFromPacketToPacket**, **NdisCopyFromPacketToPacketSafe** does not cause a bug check if system resources are low or exhausted.

The caller of **NdisCopyFromPacketToPacket** allocates the destination packet, if not the source packet as well. The packet descriptor of the destination packet should have enough chained buffer descriptors to receive the data.

If the source packet runs out of data or the destination packet out of space before the specified number of bytes has been copied, the copy operation stops. In either case, **NdisCopyFromPacketToPacket** returns the number of bytes successfully copied from the source to the destination packet.

**NdisCopyFromPacketToPacket** does not copy any out-of-band information associated with the given *Source* to the *Destination*. To copy this information, the driver can use pointers returned by [**NDIS\_OOB\_DATA\_FROM\_PACKET**](ff557084\(v=vs.85\).md) and then call [**NdisMoveMemory**](https://msdn.microsoft.com/library/Ff563625).

The driver must release any spin lock it is holding before calling **NdisCopyFromPacketToPacket**.

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Use <a href="https://msdn.microsoft.com/library/Ff561718"><strong>NdisCopyFromNetBufferToNetBuffer</strong></a>instead. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP, but use NdisCopyFromPacketToPacketSafe instead.

## -see-also

- [**NdisAllocateBuffer**](ff550736\(v=vs.85\).md)
- [**NdisAllocatePacket**](ff550774\(v=vs.85\).md)
- [**NdisCopyFromPacketToPacketSafe**](ff551071\(v=vs.85\).md)
- [**NdisMoveMemory**](https://msdn.microsoft.com/library/Ff563625)
- [**NDIS\_OOB\_DATA\_FROM\_PACKET**](ff557084\(v=vs.85\).md)
- [**NDIS\_PACKET\_OOB\_DATA**](ff557105\(v=vs.85\).md)
