---
UID: NS:storport._STOR_POWER_SETTING_INFO
tech.root: storage
title: STOR_POWER_SETTING_INFO
ms.date: 05/13/2021
targetos: Windows
description: STOR_POWER_SETTING_INFO is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiPowerSettingNotification.
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
req.typenames: STOR_POWER_SETTING_INFO, *PSTOR_POWER_SETTING_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_POWER_SETTING_INFO
 - PSTOR_POWER_SETTING_INFO
 - STOR_POWER_SETTING_INFO
f1_keywords:
 - _STOR_POWER_SETTING_INFO
 - storport/_STOR_POWER_SETTING_INFO
 - PSTOR_POWER_SETTING_INFO
 - storport/PSTOR_POWER_SETTING_INFO
 - STOR_POWER_SETTING_INFO
 - storport/STOR_POWER_SETTING_INFO
dev_langs:
 - c++
---

## -description

**STOR_POWER_SETTING_INFO** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiPowerSettingNotification**.

## -struct-fields

### -field PowerSettingGuid

The GUID of the power setting that changed.

### -field Value

Data representing the new value for the power setting.

### -field ValueLength

Length in bytes of the data pointed to by **Value.**

## -remarks

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
