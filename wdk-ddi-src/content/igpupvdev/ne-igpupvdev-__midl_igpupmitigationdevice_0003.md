---
UID: NE:igpupvdev.__MIDL_IGPUPMitigationDevice_0003
title: __MIDL_IGPUPMitigationDevice_0003 (igpupvdev.h)
description: "Learn more about: __MIDL_IGPUPMitigationDevice_0003 enumeration"
ms.date: 10/19/2018
tech.root: display
req.header: igpupvdev.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: GPUP_SAVE_RESTORE_PAUSE_STATE
targetos: Windows
f1_keywords:
 - __MIDL_IGPUPMitigationDevice_0003
 - igpupvdev/__MIDL_IGPUPMitigationDevice_0003
 - GPUP_SAVE_RESTORE_PAUSE_STATE
 - igpupvdev/GPUP_SAVE_RESTORE_PAUSE_STATE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - igpupvdev.h
api_name:
 - __MIDL_IGPUPMitigationDevice_0003
 - GPUP_SAVE_RESTORE_PAUSE_STATE
---

# __MIDL_IGPUPMitigationDevice_0003 enumeration

## -description

The **__MIDL_IGPUPMitigationDevice_0003** enumeration identifies the possible power device state values.

## -enum-fields

### -field GpupSaveInvalid

Initial state.

### -field GpupSavePartitionPersist

The physical device will be maintained; only the UMED is being reloaded.

### -field GpupSaveMaximum

Maximum value of the enumeration.

## -remarks

For more information see [Live migration on GPU-P machines](/windows-hardware/drivers/display/live-migration-on-gpup-devices).
