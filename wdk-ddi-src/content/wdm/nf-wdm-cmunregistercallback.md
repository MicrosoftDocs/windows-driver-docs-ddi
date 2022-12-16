---
UID: NF:wdm.CmUnRegisterCallback
title: CmUnRegisterCallback function (wdm.h)
description: The CmUnRegisterCallback routine unregisters a RegistryCallback routine that a CmRegisterCallback or CmRegisterCallbackEx routine previously registered.
tech.root: kernel
ms.date: 12/09/2022
keywords: ["CmUnRegisterCallback function"]
ms.keywords: CmUnRegisterCallback, CmUnRegisterCallback routine [Kernel-Mode Driver Architecture], ConfigMgrRef_13cbc14e-4652-4a3d-a87e-f6eef883f912.xml, kernel.cmunregistercallback, wdm/CmUnRegisterCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CmUnRegisterCallback
 - wdm/CmUnRegisterCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmUnRegisterCallback
---

## -description

The **CmUnRegisterCallback** routine unregisters a [RegistryCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function) routine that a [CmRegisterCallback](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback) or [CmRegisterCallbackEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex) routine previously registered.

## -parameters

### -param Cookie [in]

A LARGE_INTEGER value that identifies the callback routine to unregister. **CmRegisterCallback** provided this value when you registered the callback routine.

## -returns

**CmUnRegisterCallback** returns STATUS_SUCCESS if it succeeds or the appropriate [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code if it fails. If the *Cookie* parameter does not match any registered callback routines, **CmUnRegisterCallback** returns STATUS_INVALID_PARAMETER.

## -remarks

A driver that calls **CmRegisterCallback** or **CmRegisterCallbackEx** should call **CmUnRegisterCallback** before the driver is unloaded.

A driver must not call **CmUnRegisterCallback** from its implementation of the [RegistryCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function) routine. That call will result in a deadlock.

For more information about **CmUnRegisterCallback** and filtering registry operations, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[CmRegisterCallback](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback)

[CmRegisterCallbackEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex)

[RegistryCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function)
