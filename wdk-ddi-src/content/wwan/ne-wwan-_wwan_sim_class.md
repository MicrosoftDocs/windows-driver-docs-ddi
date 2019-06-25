---
UID: NE:wwan._WWAN_SIM_CLASS
title: _WWAN_SIM_CLASS (wwan.h)
description: The WWAN_SIM_CLASS enumeration lists the different types of Subscriber Identity Modules (SIMs) that are supported by the MB device.
old-location: netvista\wwan_sim_class.htm
tech.root: netvista
ms.assetid: 4d66874b-bb1d-43e5-a4b2-525face7de81
ms.date: 05/02/2018
ms.keywords: "*PWWAN_SIM_CLASS, PWWAN_SIM_CLASS, PWWAN_SIM_CLASS enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SIM_CLASS, WWAN_SIM_CLASS enumeration [Network Drivers Starting with Windows Vista], WwanRef_8c5184eb-4ac5-40a7-bb52-875554517f70.xml, WwanSimClassMax, WwanSimClassSimLogical, WwanSimClassSimRemote, WwanSimClassSimRemovable, WwanSimClassUnknown, _WWAN_SIM_CLASS, netvista.wwan_sim_class, wwan/PWWAN_SIM_CLASS, wwan/WWAN_SIM_CLASS, wwan/WwanSimClassMax, wwan/WwanSimClassSimLogical, wwan/WwanSimClassSimRemote, wwan/WwanSimClassSimRemovable, wwan/WwanSimClassUnknown"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_SIM_CLASS
product:
- Windows
targetos: Windows
req.typenames: WWAN_SIM_CLASS, *PWWAN_SIM_CLASS
---

# _WWAN_SIM_CLASS enumeration


## -description


The WWAN_SIM_CLASS enumeration lists the different types of Subscriber Identity Modules (SIMs) that
  are supported by the MB device.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>
 

 

