---
UID: NS:windot11.DOT11_MAC_INFO
title: DOT11_MAC_INFO (windot11.h)
description: The DOT11_MAC_INFO structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_mac_info.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_MAC_INFO structure"]
ms.keywords: "*PDOT11_MAC_INFO, DOT11_MAC_INFO, DOT11_MAC_INFO structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_435a3e63-9d42-4b74-8280-d1a0456e3dbf.xml, PDOT11_MAC_INFO, PDOT11_MAC_INFO structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_mac_info, windot11/DOT11_MAC_INFO, windot11/PDOT11_MAC_INFO"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.irql: 
targetos: Windows
req.typenames: DOT11_MAC_INFO, *PDOT11_MAC_INFO
f1_keywords:
 - DOT11_MAC_INFO
 - windot11/DOT11_MAC_INFO
 - PDOT11_MAC_INFO
 - windot11/PDOT11_MAC_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_MAC_INFO
 - PDOT11_MAC_INFO
---

# DOT11_MAC_INFO structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_MAC_INFO structure specifies a new 802.11 MAC entity that the 802.11 miniport driver has
  created.

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

## -syntax

```cpp
typedef struct DOT11_MAC_INFO {
  ULONG             uReserved;
  ULONG             uNdisPortNumber;
  DOT11_MAC_ADDRESS MacAddr;
} DOT11_MAC_INFO, *PDOT11_MAC_INFO;
```

## -remarks

This structure is used with
    <a href="/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a>.

## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a>

