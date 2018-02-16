---
UID: NE:wwan._WWAN_SIM_CLASS
title: "_WWAN_SIM_CLASS"
author: windows-driver-content
description: The WWAN_SIM_CLASS enumeration lists the different types of Subscriber Identity Modules (SIMs) that are supported by the MB device.
old-location: netvista\wwan_sim_class.htm
old-project: netvista
ms.assetid: 4d66874b-bb1d-43e5-a4b2-525face7de81
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wwan/WwanSimClassSimRemovable, WwanSimClassMax, wwan/WwanSimClassUnknown, _WWAN_SIM_CLASS, *PWWAN_SIM_CLASS, wwan/WwanSimClassMax, netvista.wwan_sim_class, PWWAN_SIM_CLASS, WwanSimClassSimRemovable, wwan/PWWAN_SIM_CLASS, wwan/WWAN_SIM_CLASS, wwan/WwanSimClassSimRemote, WwanRef_8c5184eb-4ac5-40a7-bb52-875554517f70.xml, WWAN_SIM_CLASS enumeration [Network Drivers Starting with Windows Vista], WwanSimClassUnknown, WwanSimClassSimRemote, PWWAN_SIM_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SIM_CLASS, wwan/WwanSimClassSimLogical, WwanSimClassSimLogical
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
-	WWAN_SIM_CLASS
product: Windows
targetos: Windows
req.typenames: "*PWWAN_SIM_CLASS, WWAN_SIM_CLASS"
req.product: Windows 10 or later.
---

# _WWAN_SIM_CLASS enumeration


## -description


The WWAN_SIM_CLASS enumeration lists the different types of Subscriber Identity Modules (SIMs) that
  are supported by the MB device.


## -syntax


````
typedef enum _WWAN_SIM_CLASS { 
  WwanSimClassUnknown       = 0,
  WwanSimClassSimLogical,
  WwanSimClassSimRemovable,
  WwanSimClassSimRemote,
  WwanSimClassMax
} WWAN_SIM_CLASS, *PWWAN_SIM_CLASS;
````


## -enum-fields




### -field WwanSimClassUnknown

The device supports an unknown class of SIM.


### -field WwanSimClassSimLogical

The device supports a logical or embedded SIM.


### -field WwanSimClassSimRemovable

The device supports a removable SIM.


### -field WwanSimClassSimRemote

The device supports a remote SIM that is not physically attached to MB device. For example, a
     tethered cellular telephone modem.


### -field WwanSimClassMax

The total number of supported SIM classes.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_device_caps.md">WWAN_DEVICE_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SIM_CLASS enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

