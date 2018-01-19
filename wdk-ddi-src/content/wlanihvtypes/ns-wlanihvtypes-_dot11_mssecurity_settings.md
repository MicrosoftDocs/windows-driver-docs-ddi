---
UID: NS:wlanihvtypes._DOT11_MSSECURITY_SETTINGS
title: _DOT11_MSSECURITY_SETTINGS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mssecurity_settings.htm
old-project: netvista
ms.assetid: b80a06f0-7774-4bf1-9101-a466999246d6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_MSSECURITY_SETTINGS, *PDOT11_MSSECURITY_SETTINGS, DOT11_MSSECURITY_SETTINGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlanihvtypes.h
req.include-header: Wlanihv.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_MSSECURITY_SETTINGS
req.alt-loc: wlanihvtypes.h
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
req.typenames: *PDOT11_MSSECURITY_SETTINGS, DOT11_MSSECURITY_SETTINGS
req.product: Windows 10 or later.
---

# _DOT11_MSSECURITY_SETTINGS structure



## -description

## -syntax

````
typedef struct _DOT11_MSSECURITY_SETTINGS {
  DOT11_AUTH_ALGORITHM   dot11AuthAlgorithm;
  DOT11_CIPHER_ALGORITHM dot11CipherAlgorithm;
  BOOL                   fOneXEnabled;
  EAP_METHOD_TYPE        eapMethodType;
  DWORD                  dwEapConnectionDataLen;
  BYTE                   *pEapConnectionData;
} DOT11_MSSECURITY_SETTINGS, *PDOT11_MSSECURITY_SETTINGS;
````


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


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_auth_algorithm.md">DOT11_AUTH_ALGORITHM</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes-_dot11_cipher_algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MSSECURITY_SETTINGS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

