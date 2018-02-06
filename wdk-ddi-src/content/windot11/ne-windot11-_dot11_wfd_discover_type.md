---
UID: NE:windot11._DOT11_WFD_DISCOVER_TYPE
title: "_DOT11_WFD_DISCOVER_TYPE"
author: windows-driver-content
description: The DOT11_WFD_DISCOVER_TYPE enumeration indicates the mode of Wi-Fi Direct device discovery.
old-location: netvista\dot11_wfd_discover_type.htm
old-project: netvista
ms.assetid: B50C7FD5-5AE4-4BF3-9FD7-F006F4B6BAAF
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: dot11_wfd_discover_type_auto, DOT11_WFD_DISCOVER_TYPE, dot11_wfd_discover_type_find_only, windot11/dot11_wfd_discover_type_scan_only, *PDOT11_WFD_DISCOVER_TYPE, windot11/dot11_wfd_discover_type_auto, netvista.dot11_wfd_discover_type, _DOT11_WFD_DISCOVER_TYPE, dot11_wfd_discover_type_forced, windot11/dot11_wfd_discover_type_find_only, windot11/DOT11_WFD_DISCOVER_TYPE, dot11_wfd_discover_type_scan_social_channels, DOT11_WFD_DISCOVER_TYPE enumeration [Network Drivers Starting with Windows Vista], windot11/dot11_wfd_discover_type_forced, windot11/dot11_wfd_discover_type_scan_social_channels, dot11_wfd_discover_type_scan_only
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
-	HeaderDef
apilocation:
-	Windot11.h
apiname:
-	DOT11_WFD_DISCOVER_TYPE
product: Windows
targetos: Windows
req.typenames: DOT11_WFD_DISCOVER_TYPE, *PDOT11_WFD_DISCOVER_TYPE
req.product: Windows 10 or later.
---

# _DOT11_WFD_DISCOVER_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_DISCOVER_TYPE</b> enumeration indicates  the mode of Wi-Fi Direct device discovery.


## -syntax


````
typedef enum _DOT11_WFD_DISCOVER_TYPE { 
  dot11_wfd_discover_type_scan_only             = 1,
  dot11_wfd_discover_type_find_only             = 2,
  dot11_wfd_discover_type_auto                  = 3,
  dot11_wfd_discover_type_scan_social_channels  = 4,
  dot11_wfd_discover_type_forced                = 0x80000000
} DOT11_WFD_DISCOVER_TYPE;
````


## -enum-fields




### -field dot11_wfd_discover_type_scan_only

Device discovery occurs only during the scan phase. During the scan phase, Wi-Fi Direct devices should scan each social channel at least once every 250ms.


### -field dot11_wfd_discover_type_find_only

Device discovery occurs only during the find phase.


### -field dot11_wfd_discover_type_auto

Discovery mode is determined by the driver.


### -field dot11_wfd_discover_type_scan_social_channels

The WFD device must perform device discovery by scanning only P2P social channels. In this setting, the device should scan each social channel at least once every 250ms.


### -field dot11_wfd_discover_type_forced

A flag indicating that a complete device discovery is required. If this flag is not set, a partial discovery can be performed.


## -remarks


The <b>dot11_wfd_discover_type_forced</b> flag may be set along with only one of the other discovery modes.



## -see-also

<a href="..\windot11\ns-windot11-_dot11_wfd_discover_request.md">DOT11_WFD_DISCOVER_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451795">OID_DOT11_WFD_DISCOVER_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_WFD_DISCOVER_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

