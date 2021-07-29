---
UID: NS:storport._STOR_FILTER_RESOURCE_REQUIREMENTS
tech.root: storage
title: STOR_FILTER_RESOURCE_REQUIREMENTS
ms.date: 05/13/2021
targetos: Windows
description: STOR_FILTER_RESOURCE_REQUIREMENTS is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterFilterResourceRequirements.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_FILTER_RESOURCE_REQUIREMENTS, *PSTOR_FILTER_RESOURCE_REQUIREMENTS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_FILTER_RESOURCE_REQUIREMENTS
 - PSTOR_FILTER_RESOURCE_REQUIREMENTS
 - STOR_FILTER_RESOURCE_REQUIREMENTS
f1_keywords:
 - _STOR_FILTER_RESOURCE_REQUIREMENTS
 - storport/_STOR_FILTER_RESOURCE_REQUIREMENTS
 - PSTOR_FILTER_RESOURCE_REQUIREMENTS
 - storport/PSTOR_FILTER_RESOURCE_REQUIREMENTS
 - STOR_FILTER_RESOURCE_REQUIREMENTS
 - storport/STOR_FILTER_RESOURCE_REQUIREMENTS
dev_langs:
 - c++
---

## -description

**STOR_FILTER_RESOURCE_REQUIREMENTS** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterFilterResourceRequirements**.

## -struct-fields

### -field Version

The version of the filter. This is currently set to STOR_FILTER_RESOURCE_REQUIREMENTS_V1.

### -field Size

The size of this structure, in bytes. Set to ```sizeof(STOR_FILTER_RESOURCE_REQUIREMENTS)```.

### -field IoResourceRequirementsList

Pointer to an [**IO_RESOURCE_REQUIREMENTS_LIST**](../wdm/ns-wdm-_io_resource_requirements_list.md) structure that describes the set of resource configurations that can be used by a device.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
