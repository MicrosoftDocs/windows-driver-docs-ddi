---
UID: NS:windot11._DOT11_WFD_DEVICE_TYPE
title: "_DOT11_WFD_DEVICE_TYPE"
author: windows-driver-content
description: The DOT11_WFD_DEVICE_TYPE structure is used to specify primary and secondary device types.
old-location: netvista\dot11_wfd_device_type.htm
old-project: netvista
ms.assetid: 4AE7C35B-D2EA-4987-8195-EDD472C39681
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PDOT11_WFD_DEVICE_TYPE, windot11/PDOT11_WFD_DEVICE_TYPE, PDOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE, _DOT11_WFD_DEVICE_TYPE, netvista.dot11_wfd_device_type, PDOT11_WFD_DEVICE_TYPE structure pointer [Network Drivers Starting with Windows Vista], windot11/DOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE structure [Network Drivers Starting with Windows Vista]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
-	DOT11_WFD_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PDOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE"
req.product: Windows 10 or later.
---

# _DOT11_WFD_DEVICE_TYPE structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The <b>DOT11_WFD_DEVICE_TYPE</b> structure is used to specify primary and secondary device types.


## -syntax


````
typedef struct _DOT11_WFD_DEVICE_TYPE {
  USHORT   CategoryID;
  USHORT   SubCategoryID;
  UCHAR    OUI[4];
} DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE;
````


## -struct-fields




#### - CategoryID

The identifier of the main type category.


#### - SubCategoryID

The identifier of the type subcategory.


### -field OUI

 



#### - OUI[4]

The Organizationally Unique Identifier (OUI) assigned to a device.


## -remarks


The <b>DOT11_WFD_DEVICE_TYPE</b> data is provided in host byte-ordering. The miniport may need to convert the data to an ordering appropriate for inclusion in Peer-to-Peer Information Elements.


