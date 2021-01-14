---
UID: NS:wdm._REG_RESTORE_KEY_INFORMATION
title: _REG_RESTORE_KEY_INFORMATION (wdm.h)
description: The REG_RESTORE_KEY_INFORMATION structure contains the information for a registry key that is about to be restored.
old-location: kernel\reg_restore_key_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["REG_RESTORE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_RESTORE_KEY_INFORMATION, PREG_RESTORE_KEY_INFORMATION, PREG_RESTORE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_RESTORE_KEY_INFORMATION, REG_RESTORE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_RESTORE_KEY_INFORMATION, kernel.reg_restore_key_information, kstruct_d_493707cd-b5e8-4f28-b080-b3639060b5e9.xml, wdm/PREG_RESTORE_KEY_INFORMATION, wdm/REG_RESTORE_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista SP2 and later versions of the Windows operating system.
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
req.typenames: REG_RESTORE_KEY_INFORMATION, *PREG_RESTORE_KEY_INFORMATION
f1_keywords:
 - _REG_RESTORE_KEY_INFORMATION
 - wdm/_REG_RESTORE_KEY_INFORMATION
 - PREG_RESTORE_KEY_INFORMATION
 - wdm/PREG_RESTORE_KEY_INFORMATION
 - REG_RESTORE_KEY_INFORMATION
 - wdm/REG_RESTORE_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _REG_RESTORE_KEY_INFORMATION
 - PREG_RESTORE_KEY_INFORMATION
 - REG_RESTORE_KEY_INFORMATION
---

# _REG_RESTORE_KEY_INFORMATION structure


## -description

The <b>REG_RESTORE_KEY_INFORMATION</b> structure contains the information for a registry key that is about to be restored.

## -struct-fields

### -field Object

A pointer to a registry key object for the key whose name is about to be changed.

### -field FileHandle

A handle to the file from which the hive will be restored.

### -field Flags

<b>REG_FORCE_RESTORE</b>

0x00000008L

If specified, the restore operation is executed even if open handles exist at or beneath the location in the registry hierarchy to which the <i>hKey</i> parameter points.

<b>REG_WHOLE_HIVE_VOLATILE</b>

0x00000001L

If specified, a new, volatile (memory-only) set of registry information, or <i>hive</i>, is created. If REG_WHOLE_HIVE_VOLATILE is specified, the key identified by the <i>hKey</i> parameter must be either the HKEY_USERS or HKEY_LOCAL_MACHINE value.

<b>REG_REFRESH_HIVE</b>

0x00000002

If set, the location of the subtree that the <i>hKey</i> parameter points to is restored to its state immediately following the last flush. The subtree must not be lazy flushed (by calling <b>RegRestoreKey</b> with REG_NO_LAZY_FLUSH specified as the value of this parameter); the caller must have the trusted computing base (TCB) privilege; and the handle to which the <i>hKey</i> parameter refers must point to the root of the subtree.

### -field CallContext

Optional driver-defined context information that the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field ObjectContext

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## -remarks

Note that when a key is restored, only the last component of the path can be changed.

The REG_REFRESH_HIVE flag is opaque and a filter should not attempt to change it.

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>

