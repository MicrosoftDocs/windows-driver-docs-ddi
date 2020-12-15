---
UID: NS:wlanihvtypes._DOT11_MSSECURITY_SETTINGS
title: _DOT11_MSSECURITY_SETTINGS (wlanihvtypes.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mssecurity_settings.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_MSSECURITY_SETTINGS structure"]
ms.keywords: "*PDOT11_MSSECURITY_SETTINGS, DOT11_MSSECURITY_SETTINGS, DOT11_MSSECURITY_SETTINGS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5a71d8b6-a359-4eb3-9e1c-59327d0ca67c.xml, PDOT11_MSSECURITY_SETTINGS, PDOT11_MSSECURITY_SETTINGS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_MSSECURITY_SETTINGS, netvista.dot11_mssecurity_settings, wlanihvtypes/DOT11_MSSECURITY_SETTINGS, wlanihvtypes/PDOT11_MSSECURITY_SETTINGS"
req.header: wlanihvtypes.h
req.include-header: Wlanihv.h
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
targetos: Windows
req.typenames: DOT11_MSSECURITY_SETTINGS, *PDOT11_MSSECURITY_SETTINGS
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11_MSSECURITY_SETTINGS
 - wlanihvtypes/_DOT11_MSSECURITY_SETTINGS
 - PDOT11_MSSECURITY_SETTINGS
 - wlanihvtypes/PDOT11_MSSECURITY_SETTINGS
 - DOT11_MSSECURITY_SETTINGS
 - wlanihvtypes/DOT11_MSSECURITY_SETTINGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlanihvtypes.h
api_name:
 - DOT11_MSSECURITY_SETTINGS
---

# _DOT11_MSSECURITY_SETTINGS structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MSSECURITY_SETTINGS structure defines Microsoft security settings (from an active profile)
  needed in post-associate processing when using the Microsoft 802.1X implementation.

## -struct-fields

### -field dot11AuthAlgorithm

A
     <a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a> type that specifies
     the authentication algorithm.

### -field dot11CipherAlgorithm

A
     <a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a> type that
     specifies the cipher algorithm for data encryption and decryption.

### -field fOneXEnabled

A Boolean value that indicates whether the Microsoft 802.1X implementation is enabled. If <b>TRUE</b>,
     Microsoft 802.1X is enabled; otherwise, Microsoft 802.1X is disabled.

### -field eapMethodType

An EAP_METHOD_TYPE type that specifies the extensible authentication protocol (EAP) method. For
     information about EAP_METHOD_TYPE, see the Microsoft Windows SDK.

### -field dwEapConnectionDataLen

The size, in bytes, of the EAP connection data buffer pointed to by the
     <b>pEapConnectionData</b> member.

### -field pEapConnectionData

A pointer to the EAP connection data buffer.

## -syntax

```cpp
typedef struct _DOT11_MSSECURITY_SETTINGS {
  DOT11_AUTH_ALGORITHM   dot11AuthAlgorithm;
  DOT11_CIPHER_ALGORITHM dot11CipherAlgorithm;
  BOOL                   fOneXEnabled;
  EAP_METHOD_TYPE        eapMethodType;
  DWORD                  dwEapConnectionDataLen;
  BYTE                   *pEapConnectionData;
} DOT11_MSSECURITY_SETTINGS, *PDOT11_MSSECURITY_SETTINGS;
```

## -see-also

<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>



<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
