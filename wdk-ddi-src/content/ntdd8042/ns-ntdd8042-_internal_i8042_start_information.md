---
UID: NS:ntdd8042._INTERNAL_I8042_START_INFORMATION
title: _INTERNAL_I8042_START_INFORMATION (ntdd8042.h)
description: INTERNAL_I8042_START_INFORMATION specifies the interrupt object that an optional, vendor-supplied, upper-level filter device driver can use to synchronize its operation with an I8042prt ISR.
old-location: hid\internal_i8042_start_information.htm
tech.root: hid
ms.assetid: 8ceaa9de-195f-4a89-bc3e-323256097248
ms.date: 04/30/2018
keywords: ["INTERNAL_I8042_START_INFORMATION structure"]
ms.keywords: "*PINTERNAL_I8042_START_INFORMATION, INTERNAL_I8042_START_INFORMATION, INTERNAL_I8042_START_INFORMATION structure [Human Input Devices], PINTERNAL_I8042_START_INFORMATION, PINTERNAL_I8042_START_INFORMATION structure pointer [Human Input Devices], _INTERNAL_I8042_START_INFORMATION, hid.internal_i8042_start_information, i8042ref_bf7bcffd-5c6b-47b4-be53-2b543990b2fa.xml, ntdd8042/INTERNAL_I8042_START_INFORMATION, ntdd8042/PINTERNAL_I8042_START_INFORMATION"
f1_keywords:
 - "ntdd8042/INTERNAL_I8042_START_INFORMATION"
 - "INTERNAL_I8042_START_INFORMATION"
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
- ntdd8042.h
api_name:
- INTERNAL_I8042_START_INFORMATION
targetos: Windows
req.typenames: INTERNAL_I8042_START_INFORMATION, *PINTERNAL_I8042_START_INFORMATION
---

# _INTERNAL_I8042_START_INFORMATION structure


## -description


INTERNAL_I8042_START_INFORMATION specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/">interrupt object</a> that an optional, vendor-supplied, upper-level filter device driver can use to synchronize its operation with an I8042prt ISR. 


## -struct-fields




### -field Size

Specifies the size, in bytes, of an INTERNAL_I8042_START_INFORMATION structure.


### -field InterruptObject

Pointer to an interrupt object. I8042prt supplies the interrupt object.


### -field Reserved

Reserved for future use.


## -remarks



This structure is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_keyboard_start_information">IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_mouse_start_information">IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION</a> requests.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_keyboard_start_information">IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ni-ntdd8042-ioctl_internal_i8042_mouse_start_information">IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION</a>
 

 

