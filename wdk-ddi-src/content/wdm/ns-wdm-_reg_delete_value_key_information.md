---
UID: NS:wdm._REG_DELETE_VALUE_KEY_INFORMATION
title: _REG_DELETE_VALUE_KEY_INFORMATION (wdm.h)
description: The REG_DELETE_VALUE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key's value is being deleted.
old-location: kernel\reg_delete_value_key_information.htm
tech.root: kernel
ms.assetid: 7976ad9a-b40c-44b1-bc28-0bcb3b721e92
ms.date: 04/30/2018
keywords: ["_REG_DELETE_VALUE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_DELETE_VALUE_KEY_INFORMATION, PREG_DELETE_VALUE_KEY_INFORMATION, PREG_DELETE_VALUE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_DELETE_VALUE_KEY_INFORMATION, REG_DELETE_VALUE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_DELETE_VALUE_KEY_INFORMATION, kernel.reg_delete_value_key_information, kstruct_d_a95a729a-53de-4acc-a935-c2f60d7f9f18.xml, wdm/PREG_DELETE_VALUE_KEY_INFORMATION, wdm/REG_DELETE_VALUE_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_DELETE_VALUE_KEY_INFORMATION"
 - "REG_DELETE_VALUE_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
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
- REG_DELETE_VALUE_KEY_INFORMATION
targetos: Windows
req.typenames: REG_DELETE_VALUE_KEY_INFORMATION, *PREG_DELETE_VALUE_KEY_INFORMATION
---

# _REG_DELETE_VALUE_KEY_INFORMATION structure


## -description


The <b>REG_DELETE_VALUE_KEY_INFORMATION</b> structure contains information that a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can use when a registry key's value is being deleted.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose value entry is about to be deleted.


### -field ValueName

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the value entry that is about to be deleted.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes this structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to delete a value entry—for example, when a user-mode thread calls <b>RegDeleteValue</b> or when a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletevaluekey">ZwDeleteValueKey</a>.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletevaluekey">ZwDeleteValueKey</a>
 

 

