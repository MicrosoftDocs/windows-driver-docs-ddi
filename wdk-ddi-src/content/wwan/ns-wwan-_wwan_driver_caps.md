---
UID: NS:wwan._WWAN_DRIVER_CAPS
title: _WWAN_DRIVER_CAPS (wwan.h)
description: The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.
old-location: netvista\wwan_driver_caps.htm
tech.root: netvista
ms.assetid: c0696ac6-d35e-402a-8cb5-d4f23b3b8072
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DRIVER_CAPS, PWWAN_DRIVER_CAPS, PWWAN_DRIVER_CAPS structure pointer [Network Drivers Starting with Windows Vista], WWAN_DRIVER_CAPS, WWAN_DRIVER_CAPS structure [Network Drivers Starting with Windows Vista], WwanRef_6770f91c-0fe7-49a9-97cb-6af43e5b5727.xml, _WWAN_DRIVER_CAPS, netvista.wwan_driver_caps, wwan/PWWAN_DRIVER_CAPS, wwan/WWAN_DRIVER_CAPS"
ms.topic: struct
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
- WWAN_DRIVER_CAPS
product:
- Windows
targetos: Windows
req.typenames: WWAN_DRIVER_CAPS, *PWWAN_DRIVER_CAPS
---

# _WWAN_DRIVER_CAPS structure


## -description


The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.


## -struct-fields




### -field ulMajorVersion

The major version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MAJOR_VERSION.


### -field ulMinorVersion

The minor version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MINOR_VERSION.


### -field ulDriverCaps

This member is reserved for future use. Miniport drivers should set this member to the value in
     the following table.
     





#### WWAN_DRIVER_CAPS_NONE

The miniport driver has no special capabilities.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_driver_caps">NDIS_WWAN_DRIVER_CAPS</a>
 

 

