---
UID: NS:storport._STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
tech.root: storage
title: STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the STOR_RESET_BUS_SYNCHRONOUS_PARAMETER structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_RESET_BUS_SYNCHRONOUS_PARAMETER, *PSTOR_RESET_BUS_SYNCHRONOUS_PARAMETER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - PSTOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
f1_keywords:
 - _STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - storport/_STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - PSTOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - storport/PSTOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
 - storport/STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
dev_langs:
 - c++
helpviewer_keywords:
 - _STOR_RESET_BUS_SYNCHRONOUS_PARAMETER
---

## -description

**STOR_RESET_BUS_SYNCHRONOUS_PARAMETER** is the **Parameters** parameter to the miniport's [**HW_ADAPTER_CONTROL](nc-storport-hw_adapter_control.md) routine when [**ControlType**](ne-storport-scsi_adapter_control_type.md) is **ScsiAdapterResetBusSynchronous**.

## -struct-fields

### -field Version

Size, in bytes, of this structure. The structure size serves as the version number.

### -field Size

Size, in bytes, of this structure plus all of its variable-sized fields.

### -field PathId

Identifies the SCSI bus to be reset.

### -field Reserved

Reserved for future use.

## -remarks

Storport calls the miniport's [**HW_ADAPTER_CONTROL](nc-storport-hw_adapter_control.md) routine with a control type of [**ScsiAdapterResetBusSynchronous**](ne-storport-scsi_adapter_control_type.md) only if the miniport has declared support for [**StorportFeatureResetBusSynchronous**](ne-storport-storport_feature_type.md) feature.

**ScsiAdapterResetBusSynchronous** control is invoked at PASSIVE_LEVEL, so the miniport is able to do the synchronous bus reset safely.

## -see-also

[**HW_ADAPTER_CONTROL](nc-storport-hw_adapter_control.md)

[**SCSI_ADAPTER_CONTROL_TYPE**](ne-storport-scsi_adapter_control_type.md)

[**STORPORT_FEATURE_TYPE**](ne-storport-storport_feature_type.md)
