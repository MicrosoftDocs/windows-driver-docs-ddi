---
UID: NF:iddcx.IddCxCheckOsFeatureSupport
title: IddCxCheckOsFeatureSupport
ms.date: 02/17/2026
tech.root: display
targetos: Windows
description: An OS callback function that checks the specific features supported by the IddCx version.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, 26H1 (IddCx 1.11)
req.target-min-winversvr: 
req.target-type: Windows
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - iddcx.h
api_name:
 - IddCxCheckOsFeatureSupport
f1_keywords:
 - IddCxCheckOsFeatureSupport
 - iddcx/IddCxCheckOsFeatureSupport
dev_langs:
 - c++
---

# IddCxCheckOsFeatureSupport function

## -description

**IddCxCheckOsFeatureSupport** checks which specific features are supported from each 1.11 and later IddCx version.

## -parameters

### -param pOutArgs [out]

Pointer to an [**IDARG_OUT_FEATURES_SUPPORTED**](ns-iddcx-idarg_out_features_supported.md) structure that contains the output arguments of the function.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds, otherwise an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

Once a driver has confirmed it's running on an OS that supports IddCx 1.11 or later by checking the value returned by [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md), it must call **IddCxCheckOsFeatureSupport** to check which specific features are supported from each 1.11 and later IddCx version. The flags in **[IDARG_OUT_FEATURES_SUPPORTED](ns-iddcx-idarg_out_features_supported.md)::Features_1_11** tell the driver which of the IddCx 1.11 features are available.

**IddCxCheckOsFeatureSupport** isn't intended to be a replacement for [**IddCxGetVersion**](nf-iddcx-iddcxgetversion.md). Drivers should use both to determine the OS capabilities. As a general rule when new features are added, typically requiring DDI updates, the IddCx version changes and new fields are added to **IDARG_OUT_FEATURES_SUPPORTED** and a call to **IddCxCheckOsFeatureSupport** indicates which features are supported. If OS updates such as bugfixes are made that don't need a DDI update, then only the value returned by **IddCxGetVersion** is updated.

## -see-also

[**IDARG_OUT_FEATURES_SUPPORTED**](ns-iddcx-idarg_out_features_supported.md)

[IddCx versions](/windows-hardware/drivers/display/iddcx-versions)
