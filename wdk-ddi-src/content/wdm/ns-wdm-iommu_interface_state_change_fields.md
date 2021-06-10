---
UID: NS:wdm._IOMMU_INTERFACE_STATE_CHANGE_FIELDS
tech.root: kernel
title: IOMMU_INTERFACE_STATE_CHANGE_FIELDS
ms.date: 04/20/2021
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_INTERFACE_STATE_CHANGE_FIELDS, *PIOMMU_INTERFACE_STATE_CHANGE_FIELDS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - PIOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - IOMMU_INTERFACE_STATE_CHANGE_FIELDS
f1_keywords:
 - _IOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - wdm/_IOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - PIOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - wdm/PIOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - IOMMU_INTERFACE_STATE_CHANGE_FIELDS
 - wdm/IOMMU_INTERFACE_STATE_CHANGE_FIELDS
dev_langs:
 - c++
---

## -description

**IOMMU_INTERFACE_STATE_CHANGE_FIELDS** represents the fields of an [**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md), indicating the caller's wish to be notified of a change of a specific state field(s) or indicating to callback owners which states have changed.

When a caller attempts to register an [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) through [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md), these fields indicate the state(s) that the caller wants to be notified about.

When a registered [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) is invoked, the callback owner receives an [**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md); these fields indicate which states have changed.

## -struct-fields

### -field DUMMYSTRUCTNAME

A structure containing various states of an IOMMU interface.

### -field DUMMYSTRUCTNAME.AvailableDomainTypes

When set to 1, this indicates that the caller wants to be notified (via the provided callback) when the available domain types change or this indicates to callback owners that the available domain types have changed.

### -field DUMMYSTRUCTNAME.Reserved

Reserved for future fields. Currently unused.

### -field AsULONG

The consolidated values of the fields in **DUMMYSTRUCTNAME**.

## -remarks

## -see-also

[**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md)

[**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md)

[**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md)
