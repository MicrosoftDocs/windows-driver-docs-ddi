---
UID: NS:wdm._REG_LOAD_KEY_INFORMATION_V2
tech.root: kernel
title: REG_LOAD_KEY_INFORMATION_V2
ms.date: 06/21/2021
targetos: Windows
description: The REG_LOAD_KEY_INFORMATION_V2 structure contains information about a registry hive that is being loaded.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: REG_LOAD_KEY_INFORMATION_V2, *PREG_LOAD_KEY_INFORMATION_V2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _REG_LOAD_KEY_INFORMATION_V2
 - PREG_LOAD_KEY_INFORMATION_V2
 - REG_LOAD_KEY_INFORMATION_V2
f1_keywords:
 - _REG_LOAD_KEY_INFORMATION_V2
 - wdm/_REG_LOAD_KEY_INFORMATION_V2
 - PREG_LOAD_KEY_INFORMATION_V2
 - wdm/PREG_LOAD_KEY_INFORMATION_V2
 - REG_LOAD_KEY_INFORMATION_V2
 - wdm/REG_LOAD_KEY_INFORMATION_V2
dev_langs:
 - c++
---

## -description

The **REG_LOAD_KEY_INFORMATION_V2** structure contains information about a registry hive that is being loaded.

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

The access mask that was specified by the thread that is trying to load the registry key. For more information about this access mask, see the description of the *DesiredAccess* parameter of the [ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey) routine.

### -field RootHandle

An optional pointer to a location that receives the handle to the root of the hive that is being loaded. This member can be non-**NULL** if an application hive is being loaded. In all other cases, this member should be **NULL**.

### -field CallContext

Optional driver-defined context information that the driver's [RegistryCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function) routine can supply.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling the [CmSetCallbackObjectContext](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext) routine.

### -field Version

A pointer to a numeric version identifier of REG_LOAD_KEY_INFORMATION_*.

### -field FileAccessToken

A pointer to an access token (PACCESS_TOKEN) that impersonates its access level when accessing a file (this for security purposes). In this case, it is used when accessing the hive file being loaded into the registry.

## -remarks

## -see-also

[CmSetCallbackObjectContext](/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext)

[Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls)

[RegLoadKey](/windows/win32/api/winreg/nf-winreg-regloadkeya)

[RegistryCallback](/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function)

[REG_LOAD_KEY_INFORMATION](/windows-hardware/drivers/ddi/wdm/ns-wdm-_reg_load_key_information)

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[ZwCreateKey](/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey)
