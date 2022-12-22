---
UID: NF:ndis.NdisIMCopySendPerPacketInfo
tech.root: 
title: NdisIMCopySendPerPacketInfo
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
req.irql: Any level
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
 - NdisIMCopySendPerPacketInfo
f1_keywords:
 - NdisIMCopySendPerPacketInfo
 - ndis/NdisIMCopySendPerPacketInfo
dev_langs:
 - c++
helpviewer_keywords:
 - NdisIMCopySendPerPacketInfo
---

# NdisIMCopySendPerPacketInfo function

## -description

**Note**   NDIS 5. *x* has been deprecated and is superseded by NDIS 6. *x*. For new NDIS driver development, see [Network Drivers Starting with Windows Vista](https://msdn.microsoft.com/library/Ff570021). For information about porting NDIS 5. *x* drivers to NDIS 6. *x*, see [Porting NDIS 5.x Drivers to NDIS 6.0](https://msdn.microsoft.com/library/Ff570059).

**NdisIMCopySendPerPacketInfo** copies per-packet information from a packet that was sent down by an upper-level driver into a new packet to be sent down to a lower miniport driver.

## -parameters

### -param DstPacket [out]

Pointer to the destination packet descriptor in which per-packet information is to be copied.

### -param SrcPacket [in]

Pointer to the source packet descriptor from which per-packet information is copied.

## -remarks

When an intermediate driver forwards a send request from an upper-level driver to a lower miniport driver, that intermediate driver calls **NdisIMCopySendPerPacketInfo** to copy per-packet information. The intermediate driver copies the per-packet information from a packet sent down by the upper-level driver into a new packet that the intermediate driver sends down to the lower miniport driver. The intermediate driver calls **NdisIMCopySendPerPacketInfo** for each packet sent down through the stack unless the intermediate driver must modify a packet's per-packet information.

Per-packet information is contained in an [**NDIS\_PACKET\_EXTENSION**](ff557093\(v=vs.85\).md) structure and includes, for example, checksum information, Internet Protocol security information, and 802.1p priority information.

If an intermediate driver must modify a packet's per-packet information, that intermediate driver should use the [**NDIS\_PER\_PACKET\_INFO\_FROM\_PACKET**](ff557126\(v=vs.85\).md) macro to accesses the information. The driver can call this macro once for each type of per-packet information that it needs to access.

Drivers can also use the [**NDIS\_PACKET\_EXTENSION\_FROM\_PACKET**](ff557095\(v=vs.85\).md) macro, which returns a pointer to the NDIS\_PACKET\_EXTENSION structure. A driver can call this macro if it needs to access more than one type of per-packet information associated with a packet descriptor. After obtaining the pointer to the NDIS\_PACKET\_EXTENSION structure, the driver can use the appropriate array index to obtain a pointer to a particular type of per-packet information.

To copy a range of data from one packet to another, use the [**NdisCopyFromPacketToPacket**](ff551066\(v=vs.85\).md) function.

## Requirements

- Target platform: [Universal](https://go.microsoft.com/fwlink/p/?linkid=531356)
- Version: Not supported for NDIS 6.0 drivers in Windows Vista. Supported for NDIS 5.1 drivers in Windows Vista and Windows XP.
- 
## -see-also

- [**NdisCopyFromPacketToPacket**](ff551066\(v=vs.85\).md)
- [**NdisIMCopySendCompletePerPacketInfo**](ff552138\(v=vs.85\).md)
- [**NDIS\_PACKET**](ff557086\(v=vs.85\).md)
- [**NDIS\_PACKET\_EXTENSION**](ff557093\(v=vs.85\).md)
- [**NDIS\_PACKET\_EXTENSION\_FROM\_PACKET**](ff557095\(v=vs.85\).md)
- [**NDIS\_PER\_PACKET\_INFO\_FROM\_PACKET**](ff557126\(v=vs.85\).md)
