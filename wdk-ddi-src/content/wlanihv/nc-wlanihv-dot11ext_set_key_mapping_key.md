---
UID: NC:wlanihv.DOT11EXT_SET_KEY_MAPPING_KEY
title: DOT11EXT_SET_KEY_MAPPING_KEY
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetkeymappingkey.htm
old-project: netvista
ms.assetid: 7fbca90d-c5cd-40d4-a284-ca059aa6cacf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extsetkeymappingkey, Dot11ExtSetKeyMappingKey callback function [Network Drivers Starting with Windows Vista], Dot11ExtSetKeyMappingKey, DOT11EXT_SET_KEY_MAPPING_KEY, DOT11EXT_SET_KEY_MAPPING_KEY, wlanihv/Dot11ExtSetKeyMappingKey, Native_802.11_IHV_Ext_a96af10f-97f4-406e-bc75-2cdc19564df0.xml
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
-	Dot11ExtSetKeyMappingKey
product: Windows
targetos: Windows
req.typenames: "*LPDRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXT_SET_KEY_MAPPING_KEY callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetKeyMappingKey</b> function to add or delete a cipher key from the
  key-mapping key tables of the wireless LAN (WLAN) adapter. For more information about these key types, see 
  <a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>.


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
     <mshelp:link keywords="netvista.dot11_cipher_key_mapping_key_value" tabindex="0"><b>
     DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</b></mshelp:link> structure, which defines the cipher key.


## -returns


If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.



## -remarks


A key-mapping cipher key is deleted from the adapter's key tables if the 
    <b>bDelete</b> member of the 
    <mshelp:link keywords="netvista.dot11_cipher_key_mapping_key_value" tabindex="0"><b>
    DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</b></mshelp:link> structure is set to <b>TRUE</b>.

A call to the 
    <b>Dot11ExtSetKeyMappingKey</b> function results in a set request of the 
    <mshelp:link keywords="netvista.oid_dot11_cipher_key_mapping_key" tabindex="0">
    OID_DOT11_CIPHER_KEY_MAPPING_KEY</mshelp:link> object identifier (OID) to the Native 802.11 miniport driver that
    manages the WLAN adapter.



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<mshelp:link keywords="netvista.dot11_cipher_key_mapping_key_value" tabindex="0"><b>
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</b></mshelp:link>

<a href="https://msdn.microsoft.com/1de1a420-e2ec-4716-8a03-73c9278eb33b">802.11 Cipher Key Types</a>

<mshelp:link keywords="netvista.oid_dot11_cipher_key_mapping_key" tabindex="0">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_KEY_MAPPING_KEY callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

