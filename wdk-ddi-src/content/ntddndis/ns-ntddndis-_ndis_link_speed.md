---
UID: NS:ntddndis._NDIS_LINK_SPEED
title: "_NDIS_LINK_SPEED"
author: windows-driver-content
description: The NDIS_LINK_SPEED structure specifies transmit and receive link speeds.
old-location: netvista\ndis_link_speed.htm
old-project: netvista
ms.assetid: d11155a3-b455-4c6e-83b8-7a86d8fd2aa1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PNDIS_LINK_SPEED, PNDIS_LINK_SPEED, PNDIS_LINK_SPEED structure pointer [Network Drivers Starting with Windows Vista], _NDIS_LINK_SPEED, ntddndis/PNDIS_LINK_SPEED, oid_structures_ref_c610b58c-eead-4483-96ab-c3fd62c1e846.xml, netvista.ndis_link_speed, NDIS_LINK_SPEED, NDIS_LINK_SPEED structure [Network Drivers Starting with Windows Vista], ntddndis/NDIS_LINK_SPEED"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	NDIS_LINK_SPEED
product: Windows
targetos: Windows
req.typenames: NDIS_LINK_SPEED, *PNDIS_LINK_SPEED
---

# _NDIS_LINK_SPEED structure


## -description


The NDIS_LINK_SPEED structure specifies transmit and receive link speeds.
  
  


## -syntax


````
typedef struct _NDIS_LINK_SPEED {
  ULONG64 XmitLinkSpeed;
  ULONG64 RcvLinkSpeed;
} NDIS_LINK_SPEED, *PNDIS_LINK_SPEED;
````


## -struct-fields




### -field XmitLinkSpeed

The transmit link speed in bits per second. A value of -1 in this member indicates that the
     transmit link speed is unknown.


### -field RcvLinkSpeed

The receive link speed in bits per second. A value of -1 in this member indicates that the receive
     link speed is unknown.


## -remarks



The NDIS_LINK_SPEED structure specifies link speeds in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a> OIDs.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_LINK_SPEED structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

