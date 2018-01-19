---
UID: NC:wlanihv.DOT11EXT_SET_KEY_MAPPING_KEY
title: DOT11EXT_SET_KEY_MAPPING_KEY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetkeymappingkey.htm
old-project: netvista
ms.assetid: 7fbca90d-c5cd-40d4-a284-ca059aa6cacf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Dot11ExtSetKeyMappingKey
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_KEY_MAPPING_KEY callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSetKeyMappingKey(
  _In_opt_ HANDLE                              hDot11SvcHandle,
  _In_     PDOT11_CIPHER_KEY_MAPPING_KEY_VALUE pKey
);
````


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
    <a href="netvista.oid_dot11_cipher_key_mapping_key">
    OID_DOT11_CIPHER_KEY_MAPPING_KEY</a> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="netvista.oid_dot11_cipher_key_mapping_key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_KEY_MAPPING_KEY callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

