---
UID: NE:windot11._DOT11_WFD_SCAN_TYPE
title: "_DOT11_WFD_SCAN_TYPE"
author: windows-driver-content
description: The DOT11_WFD_SCAN_TYPE enumeration indicates the type of scan used during the scan phase of device discovery.
old-location: netvista\dot11_wfd_scan_type.htm
old-project: netvista
ms.assetid: E7F76E93-79B8-48AE-A1D1-E3215E2402F8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: windot11/dot11_wfd_scan_type_auto, DOT11_WFD_SCAN_TYPE, windot11/dot11_wfd_scan_type_passive, windot11/DOT11_WFD_SCAN_TYPE, DOT11_WFD_SCAN_TYPE enumeration [Network Drivers Starting with Windows Vista], netvista.dot11_wfd_scan_type, _DOT11_WFD_SCAN_TYPE, windot11/dot11_wfd_scan_type_active, dot11_wfd_scan_type_passive, *PDOT11_WFD_SCAN_TYPE, dot11_wfd_scan_type_auto, dot11_wfd_scan_type_active
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Windot11.h
apiname:
-	DOT11_WFD_SCAN_TYPE
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WFD_SCAN_TYPE, DOT11_WFD_SCAN_TYPE"
req.product: Windows 10 or later.
---

# _DOT11_WFD_SCAN_TYPE enumeration


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_SCAN_TYPE</b> enumeration indicates the type of scan used during the scan phase of device discovery.


## -syntax


````
typedef enum _DOT11_WFD_SCAN_TYPE { 
  dot11_wfd_scan_type_active   = 1,
  dot11_wfd_scan_type_passive  = 2,
  dot11_wfd_scan_type_auto     = 3
} DOT11_WFD_SCAN_TYPE;
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_WFD_SCAN_TYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

