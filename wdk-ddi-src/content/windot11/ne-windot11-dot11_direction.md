---
UID: NE:windot11.DOT11_DIRECTION
title: DOT11_DIRECTION (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_direction.htm
tech.root: netvista
ms.assetid: 83a83af9-314a-49c1-b241-a0ef0716f83a
ms.date: 02/16/2018
ms.keywords: "*PDOT11_DIRECTION, DOT11_DIRECTION, DOT11_DIRECTION enumeration [Network Drivers Starting with Windows Vista], DOT11_DIR_BOTH, DOT11_DIR_INBOUND, DOT11_DIR_OUTBOUND, Native_802.11_data_types_aef66faf-de2c-42f1-a213-ed12ea7ef583.xml, PDOT11_DIRECTION, PDOT11_DIRECTION enumeration pointer [Network Drivers Starting with Windows Vista], netvista.dot11_direction, windot11/DOT11_DIRECTION, windot11/DOT11_DIR_BOTH, windot11/DOT11_DIR_INBOUND, windot11/DOT11_DIR_OUTBOUND, windot11/PDOT11_DIRECTION"
ms.topic: enum
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- DOT11_DIRECTION
product:
- Windows
targetos: Windows
req.typenames: DOT11_DIRECTION, *PDOT11_DIRECTION
product:
- Windows 10 or later.
---

# DOT11_DIRECTION enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DIRECTION enumeration specifies whether the 802.11 station uses a cipher key to decrypt
  received packets and/or encrypt transmitted packets.


## -syntax


```cpp
typedef enum DOT11_DIRECTION {
  DOT11_DIR_INBOUND   = 1,
  DOT11_DIR_OUTBOUND  = 2,
  DOT11_DIR_BOTH      = 3
} DOT11_DIRECTION, *PDOT11_DIRECTION;
```


## -enum-fields




### -field DOT11_DIR_INBOUND

The 802.11 station uses the cipher key to decrypt packets received from the access point (AP) or
     peer station.


### -field DOT11_DIR_OUTBOUND

The 802.11 station uses the cipher key to encrypt packets transmitted to the AP or peer
     station.


### -field DOT11_DIR_BOTH

The 802.11 station uses the cipher key for packets received from or transmitted to the AP or peer
     station.


## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">Dot11ExtSetDefaultKey</a>



<a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a>



 

 


