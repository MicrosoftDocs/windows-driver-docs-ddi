---
UID: NF:wdm.EtwUnregister
title: EtwUnregister function (wdm.h)
description: The EtwUnregister function unregisters the event provider and must be called before the provider exits.
tech.root: devtest
ms.date: 02/15/2023
keywords: ["EtwUnregister function"]
ms.keywords: EtwUnregister, EtwUnregister function [Driver Development Tools], devtest.etwunregister, etw_km_04787c1b-049f-4b92-b75c-3da660d51164.xml, wdm/EtwUnregister
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe; Ntdll.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EtwUnregister
 - wdm/EtwUnregister
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - EtwUnregister
---

## -description

The **EtwUnregister** function unregisters the event provider and must be called before the provider exits.

## -parameters

### -param RegHandle [in]

A pointer to the provider registration handle, which is returned by the **EtwRegister** function if the event provider registration is successful.

## -returns

The **EtwUnregister** function returns a status code of STATUS_SUCCESS if the event provider was successfully unregistered with ETW.

## -remarks

After tracing is complete, a driver must call the **EtwUnregister** function to unregister the provider. For every call to **EtwRegister** there must be a corresponding call to **EtwUnregister**. Failure to unregister the event provider can cause errors when the process is unloaded because the callbacks associated with the process are no longer valid. No tracing calls should be made that fall outside of the code bounded by the **EtwRegister** and **EtwUnregister** functions. For the best performance, you can call the **EtwRegister** function in your **DriverEntry** routine and the **EtwUnregister** function in your **DriverUnload** routine.

Callers of **EtwRegister** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also

[EtwRegister](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister)
