---
UID: NS:ucxroothub._ROOTHUB_30PORT_INFO_EX
title: _ROOTHUB_30PORT_INFO_EX (ucxroothub.h)
description: Provides extended USB 3.0 port information about speed.
old-location: buses\_roothub_30port_info_ex.htm
tech.root: usbref
ms.assetid: 3FA3494F-DFFF-414E-B88C-DF7C034B96C6
ms.date: 05/07/2018
ms.keywords: "*PROOTHUB_30PORT_INFO_EX, P_ROOTHUB_30PORT_INFO_EX, P_ROOTHUB_30PORT_INFO_EX structure pointer [Buses], ROOTHUB_30PORT_INFO_EX, ROOTHUB_30PORT_INFO_EX structure [Buses], _ROOTHUB_30PORT_INFO_EX, buses._roothub_30port_info_ex, ucxroothub/P_ROOTHUB_30PORT_INFO_EX, ucxroothub/_ROOTHUB_30PORT_INFO_EX"
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- ucxroothub.h
api_name:
- ROOTHUB_30PORT_INFO_EX
product:
- Windows
targetos: Windows
req.typenames: ROOTHUB_30PORT_INFO_EX, *PROOTHUB_30PORT_INFO_EX
---

# _ROOTHUB_30PORT_INFO_EX structure


## -description


Provides extended USB 3.0 port information about  speed.


## -struct-fields




### -field Info

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucxroothub/ns-ucxroothub-_roothub_30port_info">ROOTHUB_30PORT_INFO</a> structure.


### -field MaxSpeedsCount

Maximum number of speeds.


### -field SpeedsCount

The count of bus speeds supported.


### -field Speeds

A pointer to a <b>USB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED</b> structure that describes the USB 3.1capability's sublink speed attributes. For structure declaration, see Usbspec.h

