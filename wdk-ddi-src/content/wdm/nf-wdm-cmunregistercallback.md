---
UID: NF:wdm.CmUnRegisterCallback
title: CmUnRegisterCallback function (wdm.h)
description: The CmUnRegisterCallback routine unregisters a RegistryCallback routine that a CmRegisterCallback or CmRegisterCallbackEx routine previously registered.
old-location: kernel\cmunregistercallback.htm
tech.root: kernel
ms.assetid: 6e291139-d7d3-4927-ad01-b09bddb0b945
ms.date: 04/30/2018
keywords: ["CmUnRegisterCallback function"]
ms.keywords: CmUnRegisterCallback, CmUnRegisterCallback routine [Kernel-Mode Driver Architecture], ConfigMgrRef_13cbc14e-4652-4a3d-a87e-f6eef883f912.xml, kernel.cmunregistercallback, wdm/CmUnRegisterCallback
f1_keywords:
 - "wdm/CmUnRegisterCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CmUnRegisterCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# CmUnRegisterCallback function


## -description


The <b>CmUnRegisterCallback</b> routine unregisters a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine that a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> routine previously registered.


## -parameters




### -param Cookie [in]

A LARGE_INTEGER value that identifies the callback routine to unregister. <b>CmRegisterCallback</b> provided this value when you registered the callback routine. 


## -returns



<b>CmUnRegisterCallback</b> returns STATUS_SUCCESS if it succeeds or the appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> error code if it fails. If the <i>Cookie</i> parameter does not match any registered callback routines, <b>CmUnRegisterCallback</b> returns STATUS_INVALID_PARAMETER.




## -remarks



A driver that calls <b>CmRegisterCallback</b> or <b>CmRegisterCallbackEx</b> should call <b>CmUnRegisterCallback</b> before the driver is unloaded. 

<div class="alert"><b>Note</b>  A driver must not call <b>CmRegisterCallback</b> from its implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine. That call will result in a deadlock.</div>
<div> </div>
For more information about <b>CmUnRegisterCallback</b> and filtering registry operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallback">CmRegisterCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

