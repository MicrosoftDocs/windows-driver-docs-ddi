---
UID: NS:wlantypes._DOT11_SSID
title: _DOT11_SSID
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_ssid.htm
old-project: netvista
ms.assetid: f032b0db-92a0-40ff-a80d-e263d7b2dc67
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_SSID, *PDOT11_SSID, DOT11_SSID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlantypes.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_SSID
req.alt-loc: wlantypes.h
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
req.typenames: *PDOT11_SSID, DOT11_SSID
req.product: Windows 10 or later.
---

# _DOT11_SSID structure



## -description

## -syntax

````
typedef struct _DOT11_SSID {
  ULONG uSSIDLength;
  UCHAR ucSSID[DOT11_SSID_MAX_LENGTH];
} DOT11_SSID, *PDOT11_SSID;
````


## -struct-fields

### -field uSSIDLength

The length, in bytes, of the 
     <b>ucSSID</b> array.


### -field ucSSID

The SSID.


## -remarks
The SSID that is specified by the 
    <b>ucSSID</b> member is not a null-terminated ASCII string. The length of the SSID is determined by the 
    <b>uSSIDLength</b> member.

A 
    <i>wildcard SSID</i> is an SSID whose 
    <b>uSSIDLength</b> member is set to zero. When the desired SSID is set to the wildcard SSID, the 802.11
    station can connect to any basic service set (BSS) network.


## -see-also
<dl>
<dt>
<a href="..\wlanihvtypes\ns-wlanihvtypes-_dot11ext_ihv_profile_params.md">DOT11EXT_IHV_PROFILE_PARAMS</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_association_start">
   NDIS_STATUS_DOT11_ASSOCIATION_START</a>
</dt>
<dt>
<a href="netvista.ndis_status_dot11_connection_start">
   NDIS_STATUS_DOT11_CONNECTION_START</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567360">NDIS_STATUS_DOT11_ROAMING_START</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569145">OID_DOT11_DESIRED_SSID_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569360">OID_DOT11_ENUM_BSS_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569413">OID_DOT11_SCAN_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_SSID structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

