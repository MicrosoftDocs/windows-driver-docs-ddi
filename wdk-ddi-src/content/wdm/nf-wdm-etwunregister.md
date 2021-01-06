---
UID: NF:wdm.EtwUnregister
title: EtwUnregister function (wdm.h)
description: The EtwUnregister function unregisters the event provider and must be called before the provider exits.
old-location: devtest\etwunregister.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["EtwUnregister function"]
ms.keywords: EtwUnregister, EtwUnregister function [Driver Development Tools], devtest.etwunregister, etw_km_04787c1b-049f-4b92-b75c-3da660d51164.xml, wdm/EtwUnregister
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.dll: NtosKrnl.exe
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
api_name:
 - EtwUnregister
---

# EtwUnregister function


## -description

The <b>EtwUnregister</b> function unregisters the event provider and must be called before the provider exits.

## -parameters

### -param RegHandle 

[in]
A pointer to the provider registration handle, which is returned by the <b>EtwRegister</b> function if the event provider registration is successful.

## -returns

The <b>EtwUnregister</b> function returns a status code of STATUS_SUCCESS if the event provider was successfully unregistered with ETW.

## -remarks

After tracing is complete, a driver must call the <b>EtwUnregister</b> function to unregister the provider. For every call to <b>EtwRegister</b> there must be a corresponding call to <b>EtwUnregister</b>. Failure to unregister the event provider can cause errors when the process is unloaded because the callbacks associated with the process are no longer valid. No tracing calls should be made that fall outside of the code bounded by the <b>EtwRegister</b> and <b>EtwUnregister</b> functions. For the best performance, you can call the <b>EtwRegister</b> function in your <b>DriverEntry</b> routine and the <b>EtwUnregister</b> function in your <b>DriverUnload</b> routine. 

Callers of <b>EtwRegister</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-etwregister">EtwRegister</a>
