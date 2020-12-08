---
UID: NS:kbdmou._CONNECT_DATA
title: _CONNECT_DATA (kbdmou.h)
description: CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.
old-location: hid\connect_data__kbdclass_.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["CONNECT_DATA structure"]
ms.keywords: "*PCONNECT_DATA, CONNECT_DATA, CONNECT_DATA structure [Human Input Devices], PCONNECT_DATA, PCONNECT_DATA structure pointer [Human Input Devices], _CONNECT_DATA, hid.connect_data__kbdclass_, kbdmou/CONNECT_DATA, kbdmou/PCONNECT_DATA, kref_e50b6d57-99fa-41bd-979c-de2d83922af6.xml"
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
targetos: Windows
req.typenames: CONNECT_DATA, *PCONNECT_DATA
f1_keywords:
 - _CONNECT_DATA
 - kbdmou/_CONNECT_DATA
 - PCONNECT_DATA
 - kbdmou/PCONNECT_DATA
 - CONNECT_DATA
 - kbdmou/CONNECT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - kbdmou.h
api_name:
 - CONNECT_DATA
---

# _CONNECT_DATA structure


## -description

CONNECT_DATA specifies information that Kbdclass and Mouclass use to connect to a keyboard or mouse port.

## -struct-fields

### -field ClassDeviceObject

Pointer to an upper-level class <a href="/windows-hardware/drivers/">filter device object</a> (filter DO).

### -field ClassService

Specifies the class service routine. See  <a href="/windows-hardware/drivers/ddi/kbdmou/nc-kbdmou-pservice_callback_routine">PSERVICE_CALLBACK_ROUTINE</a>.

## -remarks

The keyboard class driver uses this structure with an <a href="/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_keyboard_connect">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request; the mouse class driver uses <a href="/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_mouse_connect">IOCTL_INTERNAL_MOUSE_CONNECT</a> .
