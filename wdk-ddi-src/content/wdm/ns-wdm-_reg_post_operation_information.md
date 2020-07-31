---
UID: NS:wdm._REG_POST_OPERATION_INFORMATION
title: _REG_POST_OPERATION_INFORMATION (wdm.h)
description: The REG_POST_OPERATION_INFORMATION structure contains information about a completed registry operation that a RegistryCallback routine can use.
old-location: kernel\reg_post_operation_information.htm
tech.root: kernel
ms.assetid: 2266e816-2060-4071-bf9f-319daefbfc50
ms.date: 04/30/2018
keywords: ["_REG_POST_OPERATION_INFORMATION structure"]
ms.keywords: "*PREG_POST_OPERATION_INFORMATION, PREG_POST_OPERATION_INFORMATION, PREG_POST_OPERATION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_POST_OPERATION_INFORMATION, REG_POST_OPERATION_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_POST_OPERATION_INFORMATION, kernel.reg_post_operation_information, kstruct_d_70ca0f06-65d5-4b1b-ab66-cc44361d4e5a.xml, wdm/PREG_POST_OPERATION_INFORMATION, wdm/REG_POST_OPERATION_INFORMATION"
f1_keywords:
 - "wdm/REG_POST_OPERATION_INFORMATION"
 - "REG_POST_OPERATION_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003 and later versions of the Windows operating system, but some structure members are available only for Windows Vista and later versions.
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
- REG_POST_OPERATION_INFORMATION
targetos: Windows
req.typenames: REG_POST_OPERATION_INFORMATION, *PREG_POST_OPERATION_INFORMATION
---

# _REG_POST_OPERATION_INFORMATION structure


## -description


The <b>REG_POST_OPERATION_INFORMATION</b> structure contains information about a completed registry operation that a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can use.


## -struct-fields




### -field Object

A pointer to the registry key object for which the operation has completed. This member is valid only if the Status member of the structure is set to STATUS_SUCCESS. For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=613134">Invalid Key Object Pointers in Registry Notifications</a>.


### -field Status

The NTSTATUS-typed value that the system will return for the registry operation.


### -field PreInformation

A pointer to the structure that contains preprocessing information for the registry operation that has completed. For example, if the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine is processing a <b>RegNtPostQueryValueKey</b> operation, the <b>PreInformation</b> member points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_query_value_key_information">REG_QUERY_VALUE_KEY_INFORMATION</a> structure. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ReturnStatus

A driver-supplied NTSTATUS-typed value. If the driver's <i>RegistryCallback</i> routine returns STATUS_CALLBACK_BYPASS, the operating system uses the <b>ReturnStatus</b> member's value as the status that it returns to the thread that initiated the registry operation. (In such cases, the operating system also copies the <b>ReturnStatus</b> member's value to the <b>Status</b> member.) Otherwise, this member is ignored. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



For more information about handling post-notifications, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-notifications">Handling Notifications</a>.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_query_value_key_information">REG_QUERY_VALUE_KEY_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

