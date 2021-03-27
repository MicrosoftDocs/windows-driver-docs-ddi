---
UID: NS:storport._SCSI_SUPPORTED_CONTROL_TYPE_LIST
tech.root: storage
title: SCSI_SUPPORTED_CONTROL_TYPE_LIST
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: SCSI_SUPPORTED_CONTROL_TYPE_LIST is the structure pointed to by the Parameters parameter when a miniport's HwStorUnitControl routine is called with a ControlType of ScsiQuerySupportedUnitControlTypes or HwStorAdapterControl routine is called with a ControlType of ScsiQuerySupportedControlTypes.
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
req.typenames: SCSI_SUPPORTED_CONTROL_TYPE_LIST, *PSCSI_SUPPORTED_CONTROL_TYPE_LIST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _SCSI_SUPPORTED_CONTROL_TYPE_LIST
 - PSCSI_SUPPORTED_CONTROL_TYPE_LIST
 - SCSI_SUPPORTED_CONTROL_TYPE_LIST
f1_keywords:
 - _SCSI_SUPPORTED_CONTROL_TYPE_LIST
 - storport/_SCSI_SUPPORTED_CONTROL_TYPE_LIST
 - PSCSI_SUPPORTED_CONTROL_TYPE_LIST
 - storport/PSCSI_SUPPORTED_CONTROL_TYPE_LIST
 - SCSI_SUPPORTED_CONTROL_TYPE_LIST
 - storport/SCSI_SUPPORTED_CONTROL_TYPE_LIST
dev_langs:
 - c++
---

## -description

**SCSI_SUPPORTED_CONTROL_TYPE_LIST** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorUnitControl**](nc-storport-hw_unit_control.md) routine is called with a **ControlType** of **ScsiQuerySupportedUnitControlTypes** or [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiQuerySupportedControlTypes**.

## -struct-fields

### -field MaxControlType

The number of entries in the **SupportedTypeList** array. A miniport's implementation needs to handle the case where the value of **MaxControlType** might be larger than the **ScsiUnitControlMax** (for unit control) or **ScsiAdapterControlMax** (for adapter control) value that the driver is compiled with.

### -field SupportedTypeList

Points to a caller-allocated array of **BOOLEAN** values that indicate the unit or adapter control types implemented by the miniport driver. The port driver initializes each element to **FALSE** for both unit devices and adapters. The miniport driver must not set any element beyond **SupportedTypeList**[**MaxControlType** - 1]. See Remarks for additional details.

## -remarks

When **SCSI_SUPPORTED_CONTROL_TYPE_LIST** is being used for *unit control*, the miniport driver sets the corresponding element in the **SupportedTypeList** array to **TRUE** for each operation it supports:

- **SupportedTypeList[ScsiQuerySupportedControlTypes]**
- **SupportedTypeList[ScsiUnitUsage]**
- **SupportedTypeList[ScsiUnitStart]**
- **SupportedTypeList[ScsiUnitPower]**
- **SupportedTypeList[ScsiUnitPoFxPowerInfo]**
- **SupportedTypeList[ScsiUnitPoFxPowerRequired]**
- **SupportedTypeList[ScsiUintPoFxPowerActive]**
- **SupportedTypeList[ScsiUnitPoFxPowerSetFState]**
- **SupportedTypeList[ScsiUnitPoFxPowerControl]**
- **SupportedTypeList[ScsiUnitRemove]**
- **SupportedTypeList[ScsiUnitSurpriseRemoval]**
- **SupportedTypeList[ScsiUnitRichDescription]**
- **SupportedTypeList[ScsiUnitQueryBusType]** (Windows 10 version 20H1 and later)
- **SupportedTypeList[ScsiUnitQueryFruId]** (Windows 10 version 20H1 and later)

If a miniport indicates support for **ScsiUnitQueryBusType** or **ScsiUnitQueryFruId**, it must also call [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md) with **StorportFeatureBusTypeUnitControl** or **StorportFeatureFruIdUnitControl** set, respectively.

When **SCSI_SUPPORTED_CONTROL_TYPE_LIST** is being used for *adapter control*, the miniport driver sets the corresponding element in the **SupportedTypeList** array to **TRUE** for each operation it supports:

- **SupportedTypeList[ScsiQuerySupportedControlTypes]**
- **SupportedTypeList[ScsiStopAdapter]**
- **SupportedTypeList[ScsiRestartAdapter]**
- **SupportedTypeList[ScsiSetBootConfig]**
- **SupportedTypeList[ScsiSetRunningConfig]**
- **SupportedTypeList[ScsiPowerSettingNotification]**
- **SupportedTypeList[ScsiAdapterPower]**
- **SupportedTypeList[ScsiAdapterPoFxPowerRequired]**
- **SupportedTypeList[ScsiAdapterPoFxPowerActive]**
- **SupportedTypeList[ScsiAdapterPoFxPowerSetFState]**
- **SupportedTypeList[ScsiAdapterPoFxPowerControl]**
- **SupportedTypeList[ScsiAdapterPrepareForBusReScan]**
- **SupportedTypeList[ScsiAdapterSystemPowerHints]**
- **SupportedTypeList[ScsiAdapterFilterResourceRequirements]**
- **SupportedTypeList[ScsiAdapterPoFxMaxOperationalPower]**
- **SupportedTypeList[ScsiAdapterPoFxSetPerfState]**
- **SupportedTypeList[ScsiAdapterSurpriseRemoval]**
- **SupportedTypeList[ScsiAdapterSerialNumber]**
- **SupportedTypeList[ScsiAdapterCryptoOperation]**
- **SupportedTypeList[ScsiAdapterQueryFruId]**
- **SupportedTypeList[ScsiAdapterSetEventLogging]**

If a miniport indicates support for **ScsiAdapterQueryFruId** or **ScsiAdapterSetEventLogging**, it must also call [**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md) with **StorportFeatureFruIdAdapterControl** or **StorportFeatureSetEventLoggingAdapterControl** set, respectively.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**HwStorUnitControl**](nc-storport-hw_unit_control.md)

[**StorPortSetFeatureList**](nf-storport-storportsetfeaturelist.md)
