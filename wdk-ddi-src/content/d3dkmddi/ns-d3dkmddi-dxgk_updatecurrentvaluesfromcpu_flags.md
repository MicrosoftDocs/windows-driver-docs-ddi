---
UID: NS:d3dkmddi._DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
tech.root: display
title: DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
 - DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
f1_keywords:
 - _DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
 - d3dkmddi/_DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
 - DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
 - d3dkmddi/DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS
---

# DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS structure (d3dkmddi.h)

## -description

**DXGK_UPDATECURRENTVALUESFROMCPU_FLAGS** specifies flags to use when updating the current value of a batch of native fences from the CPU.

## -struct-fields

### -field AlwaysSignaled

To handle special cases such as the parent device of the fence being put in error, *Dxgkrnl* will provide a new **CurrentValue** as 0xFFFFFFFF and call [**DxgkDdiUpdateCurrentValuesFromCpu**](nc-d3dkmddi-dxgkddi_updatecurrentvaluesfromcpu.md) with the **AlwaysSignaled** flag set. This flag indicates to the driver that the fence object **CurrentValue** can't be relied upon to be updated as before. The driver / context management processor must ensure that when it sees a GPU wait of this fence, it must be unblocked immediately without actually queuing a wait. Similarly, when it sees a signal of this fence it should be a no-op and not touch the fence storage.

### -field NotificationOnly

OS sets this flag to inform KMD that it should not actually write a new value to **CurrentValue** location, and instead this call is just a notification that **CurrentValue** was updated and KMD should re-scan its runlist to unblock any GPU waiters that are now signaled. This flag is used to handle cross-adapter native fences, as described in [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

### -field Reserved

Reserved for system use.

### -field Value

An alternative way to access the flags.

## -remarks

For more information about native GPU fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects).

## -see-also

[**DXGKARG_UPDATECURRENTVALUESFROMCPU**](ns-d3dkmddi-dxgkarg_updatecurrentvaluesfromcpu.md)

[**DxgkDdiUpdateCurrentValuesFromCpu**](nc-d3dkmddi-dxgkddi_updatecurrentvaluesfromcpu.md)
