---
UID: NF:igpupvdev.IGPUPMigration.RestoreImmutableGpup
tech.root: display
title: IGPUPMigration::RestoreImmutableGpup
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the IGPUPMigration::RestoreImmutableGpup method.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: igpupvdev.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - igpupvdev.h
api_name:
 - IGPUPMigration::RestoreImmutableGpup
f1_keywords:
 - IGPUPMigration::RestoreImmutableGpup
 - igpupvdev/IGPUPMigration::RestoreImmutableGpup
dev_langs:
 - c++
helpviewer_keywords:
 - RestoreImmutableGpup
---

## -description

The **RestoreImmutableGpup** method is part of the [**IGPUPMigration**](nn-igpupvdev-igpupmigration.md) interface, designed to restore the immutable state of a virtual GPU (vGPU) during live migration processes.

## -parameters

### -param DeviceLuid

[in] Pointer to a [**LUID**](ns-igpupvdev-_luid.md) structure that represents the locally unique identifier (LUID) of the device whose immutable state is to be restored.

### -param Length

[in] Pointer to a variable that specifies the length in bytes of the buffer that **RestoreBuffer** points to.

### -param RestoreBuffer

[in] Pointer to a buffer that contains the immutable state of the vGPU that was previously stored.

## -returns

**RestoreImmutableGpup** returns an **HRESULT** value that indicates the status of the method call. Possible return values include, but are not limited to, the following:

| Return value | Description |
|--------------|-------------|
| S_OK         | The method call was successful. |
| E_INVALIDARG | The buffer is not large enough to store the immutable state. |

## -remarks

For more information see [Live migration on GPU-P machines](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**SaveImmutableGpup**](nf-igpupvdev-igpupmigration-saveimmutablegpup.md)
