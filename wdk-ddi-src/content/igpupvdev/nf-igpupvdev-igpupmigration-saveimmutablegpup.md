---
UID: NF:igpupvdev.IGPUPMigration.SaveImmutableGpup
tech.root: display
title: IGPUPMigration::SaveImmutableGpup
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the IGPUPMigration::SaveImmutableGpup method.
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
 - IGPUPMigration::SaveImmutableGpup
f1_keywords:
 - IGPUPMigration::SaveImmutableGpup
 - igpupvdev/IGPUPMigration::SaveImmutableGpup
dev_langs:
 - c++
helpviewer_keywords:
 - SaveImmutableGpup
---

## -description

The **SaveImmutableGpup** method is part of the [**IGPUPMigration**](nn-igpupvdev-igpupmigration.md) interface, designed to save the immutable state of a virtual GPU (vGPU) during live migration processes.

## -parameters

### -param DeviceLuid

[in] Pointer to a [**LUID**](ns-igpupvdev-_luid.md) structure that represents the locally unique identifier (LUID) of the device whose immutable state is to be saved.

### -param Length

[in, out] Pointer to a variable that specifies the length in bytes of the buffer that **SaveBuffer** points to. On input, this variable specifies the size of the buffer. On output, it receives the number of bytes written to the buffer.

### -param SaveBuffer

[in, out] Pointer to a caller-allocated buffer that receives the immutable state of the device.

## -returns

**SaveImmutableGpup** returns an **HRESULT** value that indicates the status of the method call. Possible return values include, but are not limited to, the following:

| Return value | Description |
|--------------|-------------|
| S_OK         | The method call was successful. |
| E_INVALIDARG | An invalid argument was passed to the method. |
| E_OUTOFMEMORY | The method failed to allocate memory for the buffer. |

## -remarks

The **SaveImmutableGpup** method captures the immutable state of a vGPU device, which remains constant throughout the device's lifetime. This state is essential for ensuring consistency during live migration.

It's typically called during the preparation phase of a live migration process, before the device's mutable state is saved.

For more information see [Live migration on GPU-P machines](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**RestoreImmutableGpup**](nf-igpupvdev-igpupmigration-restoreimmutablegpup.md)
