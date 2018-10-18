---
UID: NS:wlanihvtypes._DOT11EXT_IHV_SSID_LIST
title: "_DOT11EXT_IHV_SSID_LIST"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11ext_ihv_ssid_list.htm
tech.root: netvista
ms.assetid: 10ef8868-5a65-4ed9-9f1d-440cda30cba4
ms.date: 2/16/2018
ms.keywords: "*PDOT11EXT_IHV_SSID_LIST, DOT11EXT_IHV_SSID_LIST, DOT11EXT_IHV_SSID_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c4e6c252-de57-4173-b6e1-df48dca0404f.xml, PDOT11EXT_IHV_SSID_LIST, PDOT11EXT_IHV_SSID_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11EXT_IHV_SSID_LIST, netvista.dot11ext_ihv_ssid_list, wlanihvtypes/DOT11EXT_IHV_SSID_LIST, wlanihvtypes/PDOT11EXT_IHV_SSID_LIST"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wlanihvtypes.h
api_name:
-	DOT11EXT_IHV_SSID_LIST
product:
- Windows
targetos: Windows
req.typenames: DOT11EXT_IHV_SSID_LIST, *PDOT11EXT_IHV_SSID_LIST
req.product: Windows 10 or later.
---

# _DOT11EXT_IHV_SSID_LIST structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11EXT_IHV_SSID_LIST structure specifies a list of 802.11 service set identifiers
  (SSIDs).


## -syntax


```cpp
typedef struct _DOT11EXT_IHV_SSID_LIST {
  ULONG      ulCount;
  DOT11_SSID SSIDs[1];
} DOT11EXT_IHV_SSID_LIST, *PDOT11EXT_IHV_SSID_LIST;
```


## -struct-fields




### -field ulCount

The number of SSIDs in the list.


### -field SSIDs

An SSID of type
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>. This is the first SSID in the
     list.


## -remarks



An SSID is a string that identifies a set of interconnected basic service sets (BSSs).




## -see-also

<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>



 

 


