---
UID: NS:windot11.DOT11_MAC_INFO
title: DOT11_MAC_INFO (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_info.htm
tech.root: netvista
ms.assetid: 0ca8814c-e91a-4f6a-b797-c440abf5cdd2
ms.date: 02/16/2018
ms.keywords: "*PDOT11_MAC_INFO, DOT11_MAC_INFO, DOT11_MAC_INFO structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_435a3e63-9d42-4b74-8280-d1a0456e3dbf.xml, PDOT11_MAC_INFO, PDOT11_MAC_INFO structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_mac_info, windot11/DOT11_MAC_INFO, windot11/PDOT11_MAC_INFO"
ms.topic: struct
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_MAC_INFO
product:
- Windows
targetos: Windows
req.typenames: DOT11_MAC_INFO, *PDOT11_MAC_INFO
product:
- Windows 10 or later.
---

# DOT11_MAC_INFO structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MAC_INFO structure specifies a new 802.11 MAC entity that the 802.11 miniport driver has
  created.


## -syntax


```cpp
typedef struct DOT11_MAC_INFO {
  ULONG             uReserved;
  ULONG             uNdisPortNumber;
  DOT11_MAC_ADDRESS MacAddr;
} DOT11_MAC_INFO, *PDOT11_MAC_INFO;
```


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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a>.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_port_characteristics.md">NDIS_PORT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a>



 

 


