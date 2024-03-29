---
UID: NS:wdm._REG_LOAD_KEY_INFORMATION
title: _REG_LOAD_KEY_INFORMATION (wdm.h)
description: The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded.
tech.root: kernel
ms.date: 06/14/2021
keywords: ["REG_LOAD_KEY_INFORMATION structure"]
ms.keywords: "*PREG_LOAD_KEY_INFORMATION, PREG_LOAD_KEY_INFORMATION, PREG_LOAD_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_LOAD_KEY_INFORMATION, REG_LOAD_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_LOAD_KEY_INFORMATION, kernel.reg_load_key_information, kstruct_d_31dae695-0a6f-4309-9c39-25c2df4a5b23.xml, wdm/PREG_LOAD_KEY_INFORMATION, wdm/REG_LOAD_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt:
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
req.typenames: REG_LOAD_KEY_INFORMATION, *PREG_LOAD_KEY_INFORMATION
f1_keywords:
 - _REG_LOAD_KEY_INFORMATION
 - wdm/_REG_LOAD_KEY_INFORMATION
 - PREG_LOAD_KEY_INFORMATION
 - wdm/PREG_LOAD_KEY_INFORMATION
 - REG_LOAD_KEY_INFORMATION
 - wdm/REG_LOAD_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _REG_LOAD_KEY_INFORMATION
 - PREG_LOAD_KEY_INFORMATION
 - REG_LOAD_KEY_INFORMATION
---

# _REG_LOAD_KEY_INFORMATION structure

## -description

The **REG_LOAD_KEY_INFORMATION** structure contains information about a registry hive that is being loaded.

## -struct-fields

### -field Object

A pointer to the registry key object for the root key of the hive that is about to be loaded.

### -field KeyName

A pointer to a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the name of the root key.

### -field SourceFile

A pointer to a **UNICODE_STRING** structure that contains the path name of a file that contains the registry hive information that is being loaded.

### -field Flags

Reserved for system use.

### -field TrustClassObject

Reserved for system use.

### -field UserEvent

A pointer to an event object that is signaled when the hive is unloaded.

### -field DesiredAccess

The access mask that was specified by the thread that is trying to load the registry key. For more information about this access mask, see the description of the *DesiredAccess* parameter of the [ZwCreateKey](./nf-wdm-zwcreatekey.md) routine.

### -field RootHandle

An optional pointer to a location that receives the handle to the root of the hive that is being loaded. This member can be non-**NULL** if an application hive is being loaded. In all other cases, this member should be **NULL**.

### -field CallContext

Optional driver-defined context information that the driver's [RegistryCallback](./nc-wdm-ex_callback_function.md) routine can supply.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling the [CmSetCallbackObjectContext](./nf-wdm-cmsetcallbackobjectcontext.md) routine.

### -field Reserved

Reserved for system use.

## -remarks

The operating system passes the **REG_LOAD_KEY_INFORMATION** structure to a [RegistryCallback](./nc-wdm-ex_callback_function.md) routine every time a user-mode thread calls [RegLoadKey](/windows/win32/api/winreg/nf-winreg-regloadkeya) to load a registry hive.

For more information about registry filtering operations, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[CmSetCallbackObjectContext](./nf-wdm-cmsetcallbackobjectcontext.md)

[Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls)

[RegLoadKey](/windows/win32/api/winreg/nf-winreg-regloadkeya)

[RegistryCallback](./nc-wdm-ex_callback_function.md)

[REG_LOAD_KEY_INFORMATION_V2](./ns-wdm-reg_load_key_information_v2.md)

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)