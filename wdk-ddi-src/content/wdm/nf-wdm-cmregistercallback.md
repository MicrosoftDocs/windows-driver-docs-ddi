---
UID: NF:wdm.CmRegisterCallback
title: CmRegisterCallback function (wdm.h)
description: The CmRegisterCallback routine is obsolete for Windows Vista and later operating system versions. Use CmRegisterCallbackEx instead.The CmRegisterCallback routine registers a RegistryCallback routine.
old-location: kernel\cmregistercallback.htm
tech.root: kernel
ms.assetid: 1c7d1f90-f34b-4a93-bce2-581abe7cdc39
ms.date: 04/30/2018
ms.keywords: CmRegisterCallback, CmRegisterCallback routine [Kernel-Mode Driver Architecture], ConfigMgrRef_ec214e13-1342-48b5-9a31-8c6c9da57cd6.xml, kernel.cmregistercallback, wdm/CmRegisterCallback
ms.topic: function
f1_keywords:
 - "wdm/CmRegisterCallback"
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
req.irql: "<=APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CmRegisterCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# CmRegisterCallback function


## -description


The <b>CmRegisterCallback</b> routine is <b>obsolete</b> for Windows Vista and later operating system versions. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> instead.

The <b>CmRegisterCallback</b> routine registers a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine.


## -parameters




### -param Function [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine to register.


### -param Context [in, optional]

A driver-defined value that the configuration manager will pass as the <i>CallbackContext</i> parameter to the <i>RegistryCallback</i> routine


### -param Cookie [out]

A pointer to a LARGE_INTEGER variable that receives the value that identifies the callback routine. When you unregister the callback routine, pass this value as the <i>Cookie</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>. 


## -returns



<b>CmRegisterCallback</b> returns STATUS_SUCCESS if the operation succeeds or the appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> error code if it fails.




## -remarks



The <b>CmRegisterCallback</b> routine is available on Windows XP and later operating system versions. For Windows Vista and later operating system versions, you should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> instead.

A driver calls <b>CmRegisterCallback</b> to register a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine, which is called every time a thread performs an operation on the registry.

Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a> to unregister a callback routine that <b>CmRegisterCallback</b> registered.

For more information about <b>CmRegisterCallback</b> and filtering registry operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

