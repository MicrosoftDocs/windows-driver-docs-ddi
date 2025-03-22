---
UID: NC:d3dkmddi.DXGKDDI_PREPARELIVEMIGRATION
tech.root: display
title: DXGKDDI_PREPARELIVEMIGRATION
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_PREPARELIVEMIGRATION function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_PREPARELIVEMIGRATION
f1_keywords:
 - DXGKDDI_PREPARELIVEMIGRATION
 - d3dkmddi/DXGKDDI_PREPARELIVEMIGRATION
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_PREPARELIVEMIGRATION
---

# DXGKDDI_PREPARELIVEMIGRATION function (d3dkmddi.h)

## -description

*Dxgkrnl* calls KMD's **DxgkDdiPrepareLiveMigration** function to notify the driver to prepare for a live migration that is about to start.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in] A pointer to a [**DXGKARG_GPUP_PREPARE_LIVE_MIGRATION**](ns-d3dkmddi-dxgkarg_gpup_prepare_live_migration.md) structure that contains the information required to prepare for a live migration.

## -returns

**DxgkDdiPrepareLiveMigration** returns STATUS_SUCCESS if it succeeds; otherwise, it returns an appropriate NTSTATUS code.

## -remarks

A call to **DxgkDdiPrepareLiveMigration** allows the driver to configure the virtual function (VF), its scheduling, its own internal state, and anything else needed around managing the migration. The intent of this call is to establish the PF/VF scheduling policies that provide for the live migration’s ability to stream dirty content from the VRAM in the host while preserving fair performance for the VF. If the dirty tracking is reported as nonperformant, this callback is also where the dirty tracking is started.

For more information, see [Live migration on GPU-P devices](/windows-hardware/drivers/display/live-migration-on-gpup-devices).

## -see-also

[**DXGKARG_GPUP_PREPARE_LIVE_MIGRATION**](ns-d3dkmddi-dxgkarg_gpup_prepare_live_migration.md)

[**DxgkDdiEndLiveMigration**](nc-d3dkmddi-dxgkddi_endlivemigration.md)
