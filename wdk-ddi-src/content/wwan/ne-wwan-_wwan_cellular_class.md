---
UID: NE:wwan._WWAN_CELLULAR_CLASS
title: "_WWAN_CELLULAR_CLASS"
author: windows-driver-content
description: The WWAN_CELLULAR_CLASS enumeration lists the different classes of cellular technology that are supported by the MB device.
old-location: netvista\wwan_cellular_class.htm
old-project: netvista
ms.assetid: c49f40b8-feb4-4dfd-9a2b-c800f3b5343a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_CELLULAR_CLASS, PWWAN_CELLULAR_CLASS, PWWAN_CELLULAR_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_CELLULAR_CLASS, WWAN_CELLULAR_CLASS enumeration [Network Drivers Starting with Windows Vista], WwanCellularClassCdma, WwanCellularClassGsm, WwanCellularClassMax, WwanCellularClassUnknown, WwanRef_cbffbef4-6a05-4042-abf0-7495fadf869d.xml, _WWAN_CELLULAR_CLASS, netvista.wwan_cellular_class, wwan/PWWAN_CELLULAR_CLASS, wwan/WWAN_CELLULAR_CLASS, wwan/WwanCellularClassCdma, wwan/WwanCellularClassGsm, wwan/WwanCellularClassMax, wwan/WwanCellularClassUnknown"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
apiname:
-	WWAN_CELLULAR_CLASS
product: Windows
targetos: Windows
req.typenames: WWAN_CELLULAR_CLASS, *PWWAN_CELLULAR_CLASS
req.product: Windows 10 or later.
---

# _WWAN_CELLULAR_CLASS enumeration


## -description


The WWAN_CELLULAR_CLASS enumeration lists the different classes of cellular technology that are
  supported by the MB device.


## -syntax


````
typedef enum _WWAN_CELLULAR_CLASS { 
  WwanCellularClassUnknown  = 0,
  WwanCellularClassGsm,
  WwanCellularClassCdma,
  WwanCellularClassMax
} WWAN_CELLULAR_CLASS, *PWWAN_CELLULAR_CLASS;
````


## -enum-fields




### -field WwanCellularClassUnknown

The device uses an unknown cellular technology.


### -field WwanCellularClassGsm

The device uses GSM-based technology.


### -field WwanCellularClassCdma

The device uses CDMA-based technology.


### -field WwanCellularClassMax

The total number of supported cellular classes.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_CELLULAR_CLASS enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

