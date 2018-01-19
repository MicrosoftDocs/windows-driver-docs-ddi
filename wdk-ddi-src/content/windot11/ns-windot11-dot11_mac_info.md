---
UID: NS:windot11.DOT11_MAC_INFO
title: DOT11_MAC_INFO
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_info.htm
old-project: netvista
ms.assetid: 0ca8814c-e91a-4f6a-b797-c440abf5cdd2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DOT11_MAC_INFO, *PDOT11_MAC_INFO, DOT11_MAC_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_MAC_INFO
req.alt-loc: windot11.h
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
req.typenames: *PDOT11_MAC_INFO, DOT11_MAC_INFO
req.product: Windows 10 or later.
---

# DOT11_MAC_INFO structure



## -description

## -syntax

````
typedef struct DOT11_MAC_INFO {
  ULONG             uReserved;
  ULONG             uNdisPortNumber;
  DOT11_MAC_ADDRESS MacAddr;
} DOT11_MAC_INFO, *PDOT11_MAC_INFO;
````


## -struct-fields

### -field uReserved

Reserved for system use.


### -field uNdisPortNumber

A ULONG value that specifies the number of the NDIS port that the 802.11 miniport driver has
     allocated to reference a newly created 802.11 MAC entity. This value is equal to the 
     <b>PortNumber</b> member of the 
     <a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">
     NDIS_PORT_CHARACTERISTICS</a> structure.


### -field MacAddr

The media access control (MAC) address of a newly created 802.11 MAC entity.


## -remarks
This structure is used with 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569124">OID_DOT11_CREATE_MAC</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569124">OID_DOT11_CREATE_MAC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

