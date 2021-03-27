---
UID: NS:storport._STOR_MAX_OPERATIONAL_POWER
tech.root: storage
title: STOR_MAX_OPERATIONAL_POWER
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_MAX_OPERATIONAL_POWER is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterPoFxMaxOperationalPower.
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
req.typenames: STOR_MAX_OPERATIONAL_POWER, *PSTOR_MAX_OPERATIONAL_POWER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_MAX_OPERATIONAL_POWER
 - PSTOR_MAX_OPERATIONAL_POWER
 - STOR_MAX_OPERATIONAL_POWER
f1_keywords:
 - _STOR_MAX_OPERATIONAL_POWER
 - storport/_STOR_MAX_OPERATIONAL_POWER
 - PSTOR_MAX_OPERATIONAL_POWER
 - storport/PSTOR_MAX_OPERATIONAL_POWER
 - STOR_MAX_OPERATIONAL_POWER
 - storport/STOR_MAX_OPERATIONAL_POWER
dev_langs:
 - c++
---

## -description

**STOR_MAX_OPERATIONAL_POWER** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterPoFxMaxOperationalPower**.

## -struct-fields

### -field Version

Version of this structure. This is currently set to 1.

### -field Size

Size of this structure, in bytes. Set to ```sizeof(STOR_MAX_OPERATIONAL_POWER)```.

### -field Value

The maximum operational power value. **Value** in each power state (P-State) must represent a maximum power level that is relative in proportion to the other P-States.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
