---
UID: NC:wlanihv.DOT11EXT_SET_DEFAULT_KEY
title: DOT11EXT_SET_DEFAULT_KEY (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetdefaultkey.htm
tech.root: netvista
ms.assetid: 7c066a71-502a-4dc2-b117-32597c534cb6
ms.date: 02/16/2018
ms.keywords: DOT11EXT_SET_DEFAULT_KEY, Dot11ExtSetDefaultKey, Dot11ExtSetDefaultKey callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_c313f938-0a68-4470-b298-d9e6c0231268.xml, netvista.dot11extsetdefaultkey, wlanihv/Dot11ExtSetDefaultKey
f1_keywords:
 - "wlanihv/Dot11ExtSetDefaultKey"
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
- Dot11ExtSetDefaultKey
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_DEFAULT_KEY callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The IHV Extensions DLL calls the
  <b>Dot11ExtSetDefaultKey</b> function to add or delete a cipher key from the
  default key or per-station default key tables of the wireless LAN (WLAN) adapter. For more information
  about these key types, see
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-cipher-key-types">802.11 Cipher Key Types</a>.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSetDefaultKey(
  _In_opt_ HANDLE                          hDot11SvcHandle,
  _In_     PDOT11_CIPHER_DEFAULT_KEY_VALUE pKey,
  _In_     DOT11_DIRECTION                 dot11Direction
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
     <a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
     DOT11_CIPHER_DEFAULT_KEY_VALUE</a> structure, which defines the cipher key.


### -param dot11Direction [in]

A
     <a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a> value that specifies whether
     the key can be used only for received packets (DOT11_DIR_INBOUND) or both received and sent packets
     (DOT11_DIR_BOTH).



<div class="alert"><b>Note</b>  The IHV Extensions DLL must not pass a value of
      <b>DOT11_DIR_OUTBOUND</b> to this parameter.</div>



## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



A call to the
    <b>Dot11ExtSetDefaultKey</b> function results in a set request of the
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">
    OID_DOT11_CIPHER_DEFAULT_KEY</a> object identifier to the WLAN adapter.

A default cipher key is defined by setting the
    <b>MacAddr</b> member of the
    <a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
    DOT11_CIPHER_DEFAULT_KEY_VALUE</a> structure to a value of 0x000000000000. A per-station default cipher
    key is defined by setting the
    <b>MacAddr</b> member to a valid unicast media access control (MAC) address.

A cipher key is deleted from the adapter's key tables if the
    <b>bDelete</b> member of the
    <a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
    DOT11_CIPHER_DEFAULT_KEY_VALUE</a> structure is set to <b>TRUE</b>.




## -see-also

<a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/802-11-cipher-key-types">802.11 Cipher Key Types</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>



<a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
   DOT11_CIPHER_DEFAULT_KEY_VALUE</a>



 

 


