---
UID: NS:kbdmou._CONNECT_DATA
title: _CONNECT_DATA (kbdmou.h)
description: CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.
old-location: hid\connect_data__kbdclass_.htm
tech.root: hid
ms.assetid: 8fdb5b1d-bbdb-4774-875a-7cdd047286f5
ms.date: 04/30/2018
ms.keywords: "*PCONNECT_DATA, CONNECT_DATA, CONNECT_DATA structure [Human Input Devices], PCONNECT_DATA, PCONNECT_DATA structure pointer [Human Input Devices], _CONNECT_DATA, hid.connect_data__kbdclass_, kbdmou/CONNECT_DATA, kbdmou/PCONNECT_DATA, kref_e50b6d57-99fa-41bd-979c-de2d83922af6.xml"
ms.topic: struct
req.header: kbdmou.h
req.include-header: Kbdmou.h
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
- kbdmou.h
api_name:
- CONNECT_DATA
product:
- Windows
targetos: Windows
req.typenames: CONNECT_DATA, *PCONNECT_DATA
---

# _CONNECT_DATA structure


## -description


CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.


## -struct-fields




### -field ClassDeviceObject

Pointer to an upper-level class <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">filter device object</a> (filter DO).


### -field ClassService

Specifies the class service routine. See  <a href="https://msdn.microsoft.com/library/windows/hardware/ff542274">PSERVICE_CALLBACK_ROUTINE</a>.


## -remarks



The keyboard class driver uses this structure with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541273">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request; the mouse class driver uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff541294">IOCTL_INTERNAL_MOUSE_CONNECT</a> .



