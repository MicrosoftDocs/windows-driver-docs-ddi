---
UID: NF:wdm.CmSetCallbackObjectContext
title: CmSetCallbackObjectContext function (wdm.h)
description: The CmSetCallbackObjectContext routine associates specified context information with a specified registry object.
old-location: kernel\cmsetcallbackobjectcontext.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["CmSetCallbackObjectContext function"]
ms.keywords: CmSetCallbackObjectContext, CmSetCallbackObjectContext routine [Kernel-Mode Driver Architecture], ConfigMgrRef_86ecc2b5-c790-4414-973d-6d26475b211d.xml, kernel.cmsetcallbackobjectcontext, wdm/CmSetCallbackObjectContext
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
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
 - CmSetCallbackObjectContext
 - wdm/CmSetCallbackObjectContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CmSetCallbackObjectContext
---

# CmSetCallbackObjectContext function

## -description

The **CmSetCallbackObjectContext** routine associates specified context information with a specified registry object.

## -parameters

### -param Object

[in, out]
A pointer to the registry key object that the driver is providing context information for. The driver obtains this pointer from the **ResultObject** member of one of the following structures:

- [REG_CREATE_KEY_INFORMATION](./ns-wdm-_reg_create_key_information.md)

- [REG_CREATE_KEY_INFORMATION_V1](./ns-wdm-_reg_create_key_information_v1.md)

- REG_OPEN_KEY_INFORMATION

- REG_OPEN_KEY_INFORMATION_V1

### -param Cookie

[in] A pointer to a LARGE_INTEGER value that identifies the callback routine to associate the context with. The [CmRegisterCallbackEx](./nf-wdm-cmregistercallbackex.md) routine provided this value when you registered the callback routine.

### -param NewContext

[in] A pointer to driver-defined context information.

### -param OldContext

[out, optional] A pointer to a location that receives a pointer to context information that the driver previously associated with the specified object and cookie. This parameter is optional and can be **NULL**.

## -returns

**CmSetCallbackObjectContext** returns STATUS_SUCCESS or another appropriate [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values)-typed value.

## -remarks

The **CmSetCallbackObjectContext** routine is available starting with Windows Vista.

A driver's [RegistryCallback](./nc-wdm-ex_callback_function.md) routine can call **CmSetCallbackObjectContext** for any registry key object after the object has been created or opened (that is, during a post-notification for a create operation, an open operation, or any subsequent notification up to the pre-notification of handle closure).

If a driver calls **CmSetCallbackObjectContext**, the driver's *RegistryCallback* routine will receive a **RegNtCallbackObjectContextCleanup** notification after the key object's handle has been closed or after the driver calls [CmUnRegisterCallback](./nf-wdm-cmunregistercallback.md) to unregister the *RegistryCallback* routine. When the *RegistryCallback* routine receives this notification, the routine should release any resources that it allocated for the object's context.

For more information about **CmSetCallbackObjectContext** and filtering registry operations, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[CmRegisterCallbackEx](./nf-wdm-cmregistercallbackex.md)

[CmUnRegisterCallback](./nf-wdm-cmunregistercallback.md)

[REG_CREATE_KEY_INFORMATION](./ns-wdm-_reg_create_key_information.md)

[REG_CREATE_KEY_INFORMATION_V1](./ns-wdm-_reg_create_key_information_v1.md)

[RegistryCallback](./nc-wdm-ex_callback_function.md)