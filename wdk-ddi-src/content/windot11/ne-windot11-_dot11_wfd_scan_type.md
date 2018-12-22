---
UID: NE:windot11._DOT11_WFD_SCAN_TYPE
title: "_DOT11_WFD_SCAN_TYPE"
description: The DOT11_WFD_SCAN_TYPE enumeration indicates the type of scan used during the scan phase of device discovery.
old-location: netvista\dot11_wfd_scan_type.htm
tech.root: netvista
ms.assetid: E7F76E93-79B8-48AE-A1D1-E3215E2402F8
ms.date: 02/16/2018
ms.keywords: "*PDOT11_WFD_SCAN_TYPE, DOT11_WFD_SCAN_TYPE, DOT11_WFD_SCAN_TYPE enumeration [Network Drivers Starting with Windows Vista], _DOT11_WFD_SCAN_TYPE, dot11_wfd_scan_type_active, dot11_wfd_scan_type_auto, dot11_wfd_scan_type_passive, netvista.dot11_wfd_scan_type, windot11/DOT11_WFD_SCAN_TYPE, windot11/dot11_wfd_scan_type_active, windot11/dot11_wfd_scan_type_auto, windot11/dot11_wfd_scan_type_passive"
ms.topic: enum
req.header: windot11.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	Windot11.h
api_name:
-	DOT11_WFD_SCAN_TYPE
product:
- Windows
targetos: Windows
req.typenames: DOT11_WFD_SCAN_TYPE, *PDOT11_WFD_SCAN_TYPE
product:
- Windows 10 or later.
---

# _DOT11_WFD_SCAN_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_SCAN_TYPE</b> enumeration indicates the type of scan used during the scan phase of device discovery.


## -syntax


```cpp
typedef enum _DOT11_WFD_SCAN_TYPE {
  dot11_wfd_scan_type_active   = 1,
  dot11_wfd_scan_type_passive  = 2,
  dot11_wfd_scan_type_auto     = 3
} DOT11_WFD_SCAN_TYPE;
```


## -enum-fields




### -field dot11_wfd_scan_type_active

Use active scanning for device discovery.


### -field dot11_wfd_scan_type_passive

Use passive scanning during device discovery.


### -field dot11_wfd_scan_type_auto

Driver selected scanning is used.


## -remarks



The system will set only one scan type at a time. The driver should use this setting to determine how it scans during device discovery.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451795">OID_DOT11_WFD_DISCOVER_REQUEST</a>



<a href="..\windot11\ns-windot11-_dot11_wfd_discover_request.md">DOT11_WFD_DISCOVER_REQUEST</a>



 

 


