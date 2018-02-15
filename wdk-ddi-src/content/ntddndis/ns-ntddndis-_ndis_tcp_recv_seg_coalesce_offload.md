---
UID: NS:ntddndis._NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
title: "_NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD"
author: windows-driver-content
description: The NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure contains the offload support state for receive segment coalescing (RSC).
old-location: netvista\ndis_tcp_recv_seg_coalesce_offload.htm
old-project: netvista
ms.assetid: F474ABFA-D811-4C03-868A-E7C23BAE2017
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure pointer [Network Drivers Starting with Windows Vista], ntddndis/NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, ntddndis/PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure [Network Drivers Starting with Windows Vista], NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, *PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, netvista.ndis_tcp_recv_seg_coalesce_offload
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
product: Windows
targetos: Windows
req.typenames: NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, *PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD
---

# _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure


## -description


The <b>NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</b>  structure contains the offload support state for receive segment coalescing (RSC).


## -syntax


````
typedef struct _NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD {
  struct {
    BOOLEAN Enabled;
  } IPv4;
  struct {
    BOOLEAN Enabled;
  } IPv6;
} NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD, *PNDIS_TCP_RECV_SEG_COALESCE_OFFLOAD;
````


## -struct-fields




### -field IPv4


### -field IPv4.Enabled

A BOOLEAN value that is set to TRUE if RSC processing on IPv4 traffic is supported. Otherwise, this member is FALSE.


### -field IPv6


### -field IPv6.Enabled

A BOOLEAN value that is set to TRUE if RSC processing on IPv6 traffic is supported. Otherwise, this member is FALSE.


## -remarks



A miniport driver advertises support for receive segment coalescing (RSC) in the Rsc member of the <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure that it passes to the <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a> function. 

The miniport driver can set the <b>IPv4.Enabled</b> member or the <b>IPv6.Enabled</b> member or both in the <b>NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD</b> structure to TRUE if it supports RSC for these protocols. The miniport driver must support RSC for 802.3 encapsulation or greater, and can support any other encapsulations. If the miniport driver does not support RSC for some encapsulation, the received packets of that encapsulation type must be indicated up the stack normally. 

To determine if a miniport driver supports RSC, NDIS drivers and other applications can query the  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a> OID which returns the NDIS_OFFLOAD structure.




## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-connection-offload-hardware-capabilities">OID_TCP_OFFLOAD_HARDWARE_CAPABILITIES</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_RECV_SEG_COALESCE_OFFLOAD structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

