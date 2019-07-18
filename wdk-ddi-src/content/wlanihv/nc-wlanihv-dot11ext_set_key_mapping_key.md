---
UID: NC:wlanihv.DOT11EXT_SET_KEY_MAPPING_KEY
title: DOT11EXT_SET_KEY_MAPPING_KEY (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetkeymappingkey.htm
tech.root: netvista
ms.assetid: 7fbca90d-c5cd-40d4-a284-ca059aa6cacf
ms.date: 02/16/2018
ms.keywords: DOT11EXT_SET_KEY_MAPPING_KEY, Dot11ExtSetKeyMappingKey, Dot11ExtSetKeyMappingKey callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_a96af10f-97f4-406e-bc75-2cdc19564df0.xml, netvista.dot11extsetkeymappingkey, wlanihv/Dot11ExtSetKeyMappingKey
ms.topic: callback
f1_keywords:
 - "wlanihv/Dot11ExtSetKeyMappingKey"
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
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
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtSetKeyMappingKey
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_KEY_MAPPING_KEY callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSetKeyMappingKey</b> function to add or delete a cipher key from the
  key-mapping key tables of the wireless LAN (WLAN) adapter. For more information about these key types, see
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-cipher-key-types">802.11 Cipher Key Types</a>.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSetKeyMappingKey(
  _In_opt_ HANDLE                              hDot11SvcHandle,
  _In_     PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE pKey
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pKey [in]

A pointer to a
     <a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
     DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a> structure, which defines the cipher key.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



A key-mapping cipher key is deleted from the adapter's key tables if the
    <b>bDelete</b> member of the
    <a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
    DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a> structure is set to <b>TRUE</b>.

A call to the
    <b>Dot11ExtSetKeyMappingKey</b> function results in a set request of the
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
    OID_DOT11_CIPHER_KEY_MAPPING_KEY</a> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-cipher-key-types">802.11 Cipher Key Types</a>



<a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


