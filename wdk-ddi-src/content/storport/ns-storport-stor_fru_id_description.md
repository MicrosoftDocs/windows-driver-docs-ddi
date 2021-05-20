---
UID: NS:storport._STOR_FRU_ID_DESCRIPTION
tech.root: storage
title: STOR_FRU_ID_DESCRIPTION
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_FRU_ID_DESCRIPTION is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiUnitQueryFruId or HwStorAdapterControl routine is called with a ControlType of ScsiAdapterQueryFruId.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: STOR_FRU_ID_DESCRIPTION, *PSTOR_FRU_ID_DESCRIPTION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_FRU_ID_DESCRIPTION
 - PSTOR_FRU_ID_DESCRIPTION
 - STOR_FRU_ID_DESCRIPTION
f1_keywords:
 - _STOR_FRU_ID_DESCRIPTION
 - storport/_STOR_FRU_ID_DESCRIPTION
 - PSTOR_FRU_ID_DESCRIPTION
 - storport/PSTOR_FRU_ID_DESCRIPTION
 - STOR_FRU_ID_DESCRIPTION
 - storport/STOR_FRU_ID_DESCRIPTION
dev_langs:
 - c++
---

## -description

STOR_FRU_ID_DESCRIPTION is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiUnitQueryFruId** or [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterQueryFruId**.

## -struct-fields

### -field Version

The version of this structure. Currently set to STOR_FRU_ID_DESCRIPTION_STRUCTURE_VERSION_1.

### -field Size

Total size of this structure, in bytes. Must be >= ```sizeof(STOR_FRU_ID_DESCRIPTION)```.

### -field Address

Pointer to a [**STOR_ADDRESS**](ns-storport-_stor_address.md) structure containing the address of the logical unit (LUN).

### -field FruId

The ID of the fault replacement unit (FRU). The FRU ID is the identifier physically printed on the hardware to uniquely identify it.  **FruId** must be <= 128 ASCII characters.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**STOR_ADDRESS**](ns-storport-_stor_address.md)
