---
UID: NS:wdm._REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
title: _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION (wdm.h)
description: The REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure contains information that a driver's RegistryCallback routine can use to free resources that the driver previously allocated for the context that is associated with a registry object.
old-location: kernel\reg_callback_context_cleanup_information.htm
tech.root: kernel
ms.assetid: 3ce6286a-6805-491d-85fc-b2c7b0a9a1fb
ms.date: 04/30/2018
keywords: ["_REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure"]
ms.keywords: "*PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, kernel.reg_callback_context_cleanup_information, kstruct_d_949535da-0c9e-474c-9d68-1e8795c7203a.xml, wdm/PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, wdm/REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION"
f1_keywords:
 - "wdm/REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION"
 - "REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
targetos: Windows
req.typenames: REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION, *PREG_CALLBACK_CONTEXT_CLEANUP_INFORMATION
---

# _REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure


## -description


The <b>REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION</b> structure contains information that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can use to free resources that the driver previously allocated for the context that is associated with a registry object.


## -struct-fields




### -field Object

A pointer to the registry key object for the key to be deleted.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>.


### -field Reserved

This member is reserved for future use.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine. When the <i>Argument1</i> parameter to the <i>RegistryCallback</i> routine is <b>RegNtCallbackObjectContextCleanup</b>, the <i>Argument2</i> parameter is a pointer to a <b>REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION</b> structure.

The driver's <i>RegistryCallback</i> routine will receive a <b>RegNtCallbackObjectContextCleanup</b> notification when the key object's reference count drops to zero (i.e. there are no outstanding handles or pointer references to the key object).

In response to this notification, the routine should release any resources that it allocated for the object's context. The <b>RegNtCallbackObjectContextCleanup</b> notification occurs when the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a> or the driver's <i>RegistryCallback</i> routine has just finished processing a <b>RegNtPreKeyHandleClose</b> notification.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmunregistercallback">CmUnRegisterCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

