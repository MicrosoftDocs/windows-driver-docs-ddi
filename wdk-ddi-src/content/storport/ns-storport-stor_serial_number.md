---
UID: NS:storport._STOR_SERIAL_NUMBER
tech.root: storage
title: STOR_SERIAL_NUMBER
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_SERIAL_NUMBER is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterSerialNumber.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_SERIAL_NUMBER, *PSTOR_SERIAL_NUMBER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_SERIAL_NUMBER
 - PSTOR_SERIAL_NUMBER
 - STOR_SERIAL_NUMBER
f1_keywords:
 - _STOR_SERIAL_NUMBER
 - storport/_STOR_SERIAL_NUMBER
 - PSTOR_SERIAL_NUMBER
 - storport/PSTOR_SERIAL_NUMBER
 - STOR_SERIAL_NUMBER
 - storport/STOR_SERIAL_NUMBER
dev_langs:
 - c++
---

## -description

**STOR_SERIAL_NUMBER** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterSerialNumber**.

## -struct-fields

### -field Version

Version of this structure. Currently set to 1.

### -field Size

Size of this structure, in bytes. Set to ```sizeof(STOR_SERIAL_NUMBER)```.

### -field Unicode

BOOLEAN value that is set TRUE if the serial number is in Unicode or FALSE if it's in ASCII.

### -field SerialNumber

NULL-terminated string representing the serial number. **SerialNumber** can contain up to 128 Unicode or ASCII characters (including the trailing NULL character). Even though there is enough space for 256 ASCII characters, do not return more than 128 characters.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
