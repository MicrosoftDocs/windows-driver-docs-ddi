---
UID: NC:wlanihv.DOT11EXT_SET_DEFAULT_KEY_ID
title: DOT11EXT_SET_DEFAULT_KEY_ID (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetdefaultkeyid.htm
tech.root: netvista
ms.assetid: 405da147-9b41-4563-8694-6619f86ed366
ms.date: 02/16/2018
ms.keywords: DOT11EXT_SET_DEFAULT_KEY_ID, Dot11ExtSetDefaultKeyId, Dot11ExtSetDefaultKeyId callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_60922941-d9b1-4d73-8029-513d127944e2.xml, netvista.dot11extsetdefaultkeyid, wlanihv/Dot11ExtSetDefaultKeyId
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtSetDefaultKeyId
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_DEFAULT_KEY_ID callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtSetDefaultKeyId</b> function to set the table index of the default or
  per-station cipher key with which the wireless LAN (WLAN) adapter uses by default when encrypting
  transmitted packet data.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSetDefaultKeyId(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     ULONG  uDefaultKeyId
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param uDefaultKeyId [in]

The index value of the key within the adapter's default or per-station cipher key tables.


For standard 802.11 cipher algorithms, such as WEP or TKIP,
     <i>uDefaultKeyId</i> must be from 0 through 3. For a proprietary cipher algorithm developed by an IHV,
     <i>uDefaultKeyId</i> can be any value within the range defined by the IHV.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



The default key identifier (ID) specifies the index of a cipher key in the adapter's default key and
    per-station default key tables that the adapter uses for data encryption. The adapter uses the cipher key
    referenced by the default key ID as the default encryption key for transmitted packets unless a
    key-mapping key exists for the destination media access control (MAC) address. For more information about
    these cipher key types, see
    <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.

A call to the
    <b>Dot11ExtSetDefaultKeyId</b> function results in a set request of the
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">
    OID_DOT11_CIPHER_DEFAULT_KEY_ID</a> object identifier (OID) to the Native 802.11 miniport driver, which
    manages the WLAN adapter.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY_ID</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>



 

 


