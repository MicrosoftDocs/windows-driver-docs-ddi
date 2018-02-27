---
UID: NS:ntddndis._NDIS_PM_WAKE_PACKET
title: "_NDIS_PM_WAKE_PACKET"
author: windows-driver-content
description: The NDIS_PM_WAKE_PACKET structure describes a network packet (known as a wake packet) that caused the network adapter to generate a wake-up event.
old-location: netvista\ndis_pm_wake_packet.htm
old-project: netvista
ms.assetid: b3d7adcf-79cd-42f4-ada2-c57de6310020
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_PM_WAKE_PACKET, NDIS_PM_WAKE_PACKET, NDIS_PM_WAKE_PACKET structure [Network Drivers Starting with Windows Vista], PNDIS_PM_WAKE_PACKET, PNDIS_PM_WAKE_PACKET structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PM_WAKE_PACKET, netvista.ndis_pm_wake_packet, ntddndis/NDIS_PM_WAKE_PACKET, ntddndis/PNDIS_PM_WAKE_PACKET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_PM_WAKE_PACKET
product: Windows
targetos: Windows
req.typenames: NDIS_PM_WAKE_PACKET, *PNDIS_PM_WAKE_PACKET
---

# _NDIS_PM_WAKE_PACKET structure


## -description


The <b>NDIS_PM_WAKE_PACKET</b> structure describes a network packet (known as a <i>wake packet</i>) that caused the network adapter to generate a wake-up event.


## -syntax


````
typedef struct _NDIS_PM_WAKE_PACKET {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  ULONG                  PatternId;
  NDIS_PM_COUNTED_STRING PatternFriendlyName;
  ULONG                  OriginalPacketSize;
  ULONG                  SavedPacketSize;
  ULONG                  SavedPacketOffset;
} NDIS_PM_WAKE_PACKET, *PNDIS_PM_WAKE_PACKET;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_PM_WAKE_PACKET</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_PM_WAKE_PACKET</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SIZEOF_PM_WAKE_PACKET_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_PM_WAKE_PACKET_REVISION_1.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field PatternId

A <b>ULONG</b> value that specifies the identifier of the wake-on-LAN (WOL) pattern that matches the wake packet. This identifier is specified by the <b>PatternId</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a> structure that is passed to the driver during an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569764">OID_PM_ADD_WOL_PATTERN</a>.


### -field PatternFriendlyName

An <a href="..\ntddndis\ns-ntddndis-_ndis_pm_counted_string.md">NDIS_PM_COUNTED_STRING</a> value that contains the friendly description of the wake pattern that is specified by the  <b>PatternId</b> member.
This value is specified by the <b>FriendlyName</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a> structure that is passed to the driver during an OID request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569764">OID_PM_ADD_WOL_PATTERN</a>.

<div class="alert"><b>Note</b>  The miniport driver does not need to initialize this member. NDIS sets the <b>PatternFriendlyName</b> member to the correct value before it passes the <b>NDIS_PM_WAKE_PACKET</b> structure to overlying drivers.

</div>
<div> </div>

### -field OriginalPacketSize

A <b>ULONG</b> value that specifies the original length, in units of bytes, of the wake packet.


### -field SavedPacketSize

A <b>ULONG</b> value that specifies the length, in units of bytes, of the wake packet data that follows this structure. 


<div class="alert"><b>Note</b>  The value of this member should at least<code> min(wake packet size, 128)</code> bytes.</div>
<div> </div>

### -field SavedPacketOffset

A <b>ULONG</b> value that specifies the offset, in units of bytes, to the wake packet data that follows this structure. The offset is measured from the start of the <b>NDIS_PM_WAKE_PACKET</b> structure to the beginning of a buffer that contains the wake packet.

<div class="alert"><b>Note</b>  The offset to the saved wake packet must be aligned on a 64-bit boundary.</div>
<div> </div>

## -remarks



The <b>NDIS_PM_WAKE_PACKET</b> structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439808">NDIS_STATUS_PM_WAKE_REASON</a> status indication. For more information about how to issue this status indication, see <a href="https://msdn.microsoft.com/F3DBE0DB-9787-4C3D-8DE3-AD47E5778B21">Issuing NDIS Wake Reason Status Indications</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_pm_wol_pattern.md">NDIS_PM_WOL_PATTERN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439808">NDIS_STATUS_PM_WAKE_REASON</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_pm_counted_string.md">NDIS_PM_COUNTED_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569764">OID_PM_ADD_WOL_PATTERN</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PM_WAKE_PACKET structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

