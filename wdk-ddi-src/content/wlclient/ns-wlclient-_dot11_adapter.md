---
UID: NS:wlclient._DOT11_ADAPTER
title: _DOT11_ADAPTER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_adapter.htm
old-project: netvista
ms.assetid: dae4c499-86c7-4f2b-bd5a-df2a62cdb77f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_ADAPTER, DOT11_ADAPTER, *PDOT11_ADAPTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlclient.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_ADAPTER
req.alt-loc: wlclient.h
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
req.typenames: DOT11_ADAPTER, *PDOT11_ADAPTER
req.product: Windows 10 or later.
---

# _DOT11_ADAPTER structure



## -description

## -syntax

````
typedef struct _DOT11_ADAPTER {
  GUID                         gAdapterId;
  LPWSTR                       pszDescription;
  DOT11_CURRENT_OPERATION_MODE Dot11CurrentOpMode;
} DOT11_ADAPTER, *PDOT11_ADAPTER;
````


## -struct-fields

### -field gAdapterId

The globally unique identifier (GUID) of the WLAN adapter.


### -field pszDescription

A description of the WLAN adapter.


### -field Dot11CurrentOpMode

The current Native 802.11 operation mode of the miniport driver instance that manages the WLAN
     adapter. The value of 
     <b>Dot11CurrentOpMode</b> is formatted as a 
     <a href="..\windot11\ns-windot11-_dot11_current_operation_mode.md">
     DOT11_CURRENT_OPERATION_MODE</a> value.


## -remarks
The operating system calls the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    handler function whenever a WLAN adapter becomes available and enabled for use, such as when a PCMCIA
    adapter is inserted. The operating system defines the WLAN adapter by passing in the DOT11_ADAPTER
    structure through the 
    <i>pDot11Adapter</i> parameter of the 
    <i>Dot11ExtIhvInitAdapter</i> function.


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-_dot11_current_operation_mode.md">DOT11_CURRENT_OPERATION_MODE</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_ADAPTER structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

