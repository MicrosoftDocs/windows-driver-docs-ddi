---
UID: NS:ntddchgr._CHANGER_SET_ACCESS
title: _CHANGER_SET_ACCESS (ntddchgr.h)
description: The CHANGER_SET_ACCESS structure is used in conjunction with theIOCTL_CHANGER_SET_ACCESS request to set the state of the device's import/export port (IEport), door, or keypad.
old-location: storage\changer_set_access.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["CHANGER_SET_ACCESS structure"]
ms.keywords: "*PCHANGER_SET_ACCESS, CHANGER_SET_ACCESS, CHANGER_SET_ACCESS structure [Storage Devices], PCHANGER_SET_ACCESS, PCHANGER_SET_ACCESS structure pointer [Storage Devices], _CHANGER_SET_ACCESS, ntddchgr/CHANGER_SET_ACCESS, ntddchgr/PCHANGER_SET_ACCESS, storage.changer_set_access, structs-changer_01f5a159-3d46-4400-8eae-87367e81ed72.xml"
req.header: ntddchgr.h
req.include-header: 
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
req.typenames: CHANGER_SET_ACCESS, *PCHANGER_SET_ACCESS
f1_keywords:
 - _CHANGER_SET_ACCESS
 - ntddchgr/_CHANGER_SET_ACCESS
 - PCHANGER_SET_ACCESS
 - ntddchgr/PCHANGER_SET_ACCESS
 - CHANGER_SET_ACCESS
 - ntddchgr/CHANGER_SET_ACCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddchgr.h
api_name:
 - _CHANGER_SET_ACCESS
 - PCHANGER_SET_ACCESS
 - CHANGER_SET_ACCESS
---

# _CHANGER_SET_ACCESS structure


## -description

The CHANGER_SET_ACCESS structure is used in conjunction with the<a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_access">IOCTL_CHANGER_SET_ACCESS</a> request to set the state of the device's import/export port (IEport), door, or keypad.

## -struct-fields

### -field Element

Contains a <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a> structure that specifies the element type and the zero-based address of the element to set. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned one of the following values:

<b>ChangerIEPortChangerDoorChangerKeypad</b>

### -field Control

Specifies the operation to perform on the element. The <b>Features0</b> member of <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports a particular category of operation.





#### LOCK_ELEMENT

Lock the door, IEport, or keypad. Valid only if CHANGER_LOCK_UNLOCK is set.



#### UNLOCK_ELEMENT

Unlock the door, IEport, or keypad. Valid only if CHANGER_LOCK_UNLOCK is set.



#### EXTEND_IEPORT

Extend the IEport. Valid only if CHANGER_OPEN_IEPORT is set.



#### RETRACT_IEPORT

Retract the IEport. Valid only if CHANGER_CLOSE_IEPORT is set.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changersetaccess">ChangerSetAccess</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_set_access">IOCTL_CHANGER_SET_ACCESS</a>

