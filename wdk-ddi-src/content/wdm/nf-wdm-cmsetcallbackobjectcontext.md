---
UID: NF:wdm.CmSetCallbackObjectContext
title: CmSetCallbackObjectContext function (wdm.h)
description: The CmSetCallbackObjectContext routine associates specified context information with a specified registry object.
old-location: kernel\cmsetcallbackobjectcontext.htm
tech.root: kernel
ms.assetid: 69e85037-5c60-404a-b251-dc1622c7d818
ms.date: 04/30/2018
ms.keywords: CmSetCallbackObjectContext, CmSetCallbackObjectContext routine [Kernel-Mode Driver Architecture], ConfigMgrRef_86ecc2b5-c790-4414-973d-6d26475b211d.xml, kernel.cmsetcallbackobjectcontext, wdm/CmSetCallbackObjectContext
f1_keywords:
 - "wdm/CmSetCallbackObjectContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CmSetCallbackObjectContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# CmSetCallbackObjectContext function


## -description


The <b>CmSetCallbackObjectContext</b> routine associates specified context information with a specified registry object.


## -parameters




### -param Object [in, out]

A pointer to the registry key object that the driver is providing context information for. The driver obtains this pointer from the <b>ResultObject</b> member of one of the following structures:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information">REG_CREATE_KEY_INFORMATION</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560957">REG_OPEN_KEY_INFORMATION</a>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>

### -param Cookie [in]

A pointer to a LARGE_INTEGER value that identifies the callback routine to associate the context with. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a> routine provided this value when you registered the callback routine.


### -param NewContext [in]

A pointer to driver-defined context information.


### -param OldContext [out, optional]

A pointer to a location that receives a pointer to context information that the driver previously associated with the specified object and cookie. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>CmSetCallbackObjectContext</b> returns STATUS_SUCCESS or another appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a>-typed value. 




## -remarks



The <b>CmSetCallbackObjectContext</b> routine is available starting with Windows Vista.

A driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can call <b>CmSetCallbackObjectContext</b> for any registry key object after the object has been created or opened (that is, during a post-notification for a create operation, an open operation, or any subsequent notification up to the pre-notification of handle closure).

If a driver calls <b>CmSetCallbackObjectContext</b>, the driver's <i>RegistryCallback</i> routine will receive a <b>RegNtCallbackObjectContextCleanup</b> notification after the key object's handle has been closed or after the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a> to unregister the <i>RegistryCallback</i> routine. When the <i>RegistryCallback</i> routine receives this notification, the routine should release any resources that it allocated for the object's context.

For more information about <b>CmSetCallbackObjectContext</b> and filtering registry operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmregistercallbackex">CmRegisterCallbackEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information">REG_CREATE_KEY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_create_key_information_v1">REG_CREATE_KEY_INFORMATION_V1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560957">REG_OPEN_KEY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560959">REG_OPEN_KEY_INFORMATION_V1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

