---
UID: NC:wlanihv.DOT11EXT_SET_DEFAULT_KEY
title: DOT11EXT_SET_DEFAULT_KEY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetdefaultkey.htm
old-project: netvista
ms.assetid: 7c066a71-502a-4dc2-b117-32597c534cb6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extsetdefaultkey, Dot11ExtSetDefaultKey callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetDefaultKey, DOT11EXT_SET_DEFAULT_KEY, DOT11EXT_SET_DEFAULT_KEY, wlanihv/Dot11ExtSetDefaultKey, Native_802.11_IHV_Ext_c313f938-0a68-4470-b298-d9e6c0231268.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtSetDefaultKey
product: Windows
targetos: Windows
req.typenames: "*PDRIVER_INFO_8W, DRIVER_INFO_8W, *LPDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXT_SET_DEFAULT_KEY callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetDefaultKey</b> function to add or delete a cipher key from the
  default key or per-station default key tables of the wireless LAN (WLAN) adapter. For more information
  about these key types, see 
  <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.


## -prototype


````
DWORD WINAPI * Dot11ExtSetDefaultKey(
  _In_opt_ HANDLE                          hDot11SvcHandle,
  _In_     PDOT11_CIPHER_DEFAULT_KEY_VALUE pKey,
  _In_     DOT11_DIRECTION                 dot11Direction
);
````


## -parameters




#### - hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


#### - pKey [in]

A pointer to a 
     <mshelp:link keywords="netvista.dot11_cipher_default_key_value" tabindex="0"><b>
     DOT11_CIPHER_DEFAULT_KEY_VALUE</b></mshelp:link> structure, which defines the cipher key.


#### - dot11Direction [in]

A 
     <a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a> value that specifies whether
     the key can be used only for received packets (DOT11_DIR_INBOUND) or both received and sent packets
     (DOT11_DIR_BOTH).
     


<div class="alert"><b>Note</b>  The IHV Extensions DLL must not pass a value of 
      <b>DOT11_DIR_OUTBOUND</b> to this parameter.</div>
<div> </div>



## -returns


If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.



## -remarks


A call to the 
    <b>Dot11ExtSetDefaultKey</b> function results in a set request of the 
    <mshelp:link keywords="netvista.oid_dot11_cipher_default_key" tabindex="0">
    OID_DOT11_CIPHER_DEFAULT_KEY</mshelp:link> object identifier to the WLAN adapter.

A default cipher key is defined by setting the 
    <b>MacAddr</b> member of the 
    <mshelp:link keywords="netvista.dot11_cipher_default_key_value" tabindex="0"><b>
    DOT11_CIPHER_DEFAULT_KEY_VALUE</b></mshelp:link> structure to a value of 0x000000000000. A per-station default cipher
    key is defined by setting the 
    <b>MacAddr</b> member to a valid unicast media access control (MAC) address.

A cipher key is deleted from the adapter's key tables if the 
    <b>bDelete</b> member of the 
    <mshelp:link keywords="netvista.dot11_cipher_default_key_value" tabindex="0"><b>
    DOT11_CIPHER_DEFAULT_KEY_VALUE</b></mshelp:link> structure is set to <b>TRUE</b>.



## -see-also

<a href="..\windot11\ne-windot11-dot11_direction.md">DOT11_DIRECTION</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-cipher-default-key-id">OID_DOT11_CIPHER_DEFAULT_KEY</a>

<mshelp:link keywords="netvista.dot11_cipher_default_key_value" tabindex="0"><b>
   DOT11_CIPHER_DEFAULT_KEY_VALUE</b></mshelp:link>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>

<a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_DEFAULT_KEY callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

