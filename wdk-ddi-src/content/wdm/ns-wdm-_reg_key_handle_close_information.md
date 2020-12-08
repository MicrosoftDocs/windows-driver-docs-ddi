---
UID: NS:wdm._REG_KEY_HANDLE_CLOSE_INFORMATION
title: _REG_KEY_HANDLE_CLOSE_INFORMATION (wdm.h)
description: The REG_KEY_HANDLE_CLOSE_INFORMATION structure contains information about a registry key whose handle is about to be closed.
old-location: kernel\reg_key_handle_close_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["REG_KEY_HANDLE_CLOSE_INFORMATION structure"]
ms.keywords: "*PREG_KEY_HANDLE_CLOSE_INFORMATION, PREG_KEY_HANDLE_CLOSE_INFORMATION, PREG_KEY_HANDLE_CLOSE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_KEY_HANDLE_CLOSE_INFORMATION, REG_KEY_HANDLE_CLOSE_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_KEY_HANDLE_CLOSE_INFORMATION, kernel.reg_key_handle_close_information, kstruct_d_26822436-a385-4b98-8179-18c661ebdb1f.xml, wdm/PREG_KEY_HANDLE_CLOSE_INFORMATION, wdm/REG_KEY_HANDLE_CLOSE_INFORMATION"
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
targetos: Windows
req.typenames: REG_KEY_HANDLE_CLOSE_INFORMATION, *PREG_KEY_HANDLE_CLOSE_INFORMATION
f1_keywords:
 - _REG_KEY_HANDLE_CLOSE_INFORMATION
 - wdm/_REG_KEY_HANDLE_CLOSE_INFORMATION
 - PREG_KEY_HANDLE_CLOSE_INFORMATION
 - wdm/PREG_KEY_HANDLE_CLOSE_INFORMATION
 - REG_KEY_HANDLE_CLOSE_INFORMATION
 - wdm/REG_KEY_HANDLE_CLOSE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - REG_KEY_HANDLE_CLOSE_INFORMATION
---

# _REG_KEY_HANDLE_CLOSE_INFORMATION structure


## -description

The <b>REG_KEY_HANDLE_CLOSE_INFORMATION</b> structure contains information about a registry key whose handle is about to be closed.

## -struct-fields

### -field Object

A pointer to the registry key object for the handle that is about to be closed.

### -field CallContext

Optional driver-defined context information that the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## -remarks

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>
