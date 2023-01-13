---
UID: NS:wdm._REG_CREATE_KEY_INFORMATION
title: REG_CREATE_KEY_INFORMATION (wdm.h)
description: Obsolete, use REG_CREATE_KEY_INFORMATION_V1 instead. The REG_CREATE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key that is being created.
tech.root: kernel
ms.date: 12/16/2022
keywords: ["REG_CREATE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION, PREG_CREATE_KEY_INFORMATION, PREG_CREATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PREG_OPEN_KEY_INFORMATION, PREG_OPEN_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_CREATE_KEY_INFORMATION, REG_CREATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], REG_OPEN_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_CREATE_KEY_INFORMATION, kernel.reg_create_key_information, kstruct_d_08c0de2c-94fb-4c4f-888c-e3485f213224.xml, wdm/PREG_CREATE_KEY_INFORMATION, wdm/PREG_OPEN_KEY_INFORMATION, wdm/REG_CREATE_KEY_INFORMATION, wdm/REG_OPEN_KEY_INFORMATION"
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
req.typenames: REG_CREATE_KEY_INFORMATION, REG_OPEN_KEY_INFORMATION, *PREG_CREATE_KEY_INFORMATION, *PREG_OPEN_KEY_INFORMATION
f1_keywords:
 - _REG_CREATE_KEY_INFORMATION
 - wdm/_REG_CREATE_KEY_INFORMATION
 - PREG_CREATE_KEY_INFORMATION
 - wdm/PREG_CREATE_KEY_INFORMATION
 - REG_CREATE_KEY_INFORMATION
 - wdm/REG_CREATE_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _REG_CREATE_KEY_INFORMATION
 - PREG_CREATE_KEY_INFORMATION
 - REG_CREATE_KEY_INFORMATION
---

## -description

Obsolete. Starting with Windows 7, use [**REG_CREATE_KEY_INFORMATION_V1**](./ns-wdm-_reg_create_key_information_v1.md), the V1 version of this structure instead.

The **REG_CREATE_KEY_INFORMATION** structure contains information that a driver's [RegistryCallback](./nc-wdm-ex_callback_function.md) routine can use when a registry key that is being created.

## -struct-fields

### -field CompleteName

A pointer to a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the path of the new registry key. The path can be absolute or relative. If the path is absolute, this structure contains a fully qualified path that starts with the "\\" character. For an absolute path, the **RootObject** member specifies the **\REGISTRY** key, which is the root directory of the registry tree. If the path is relative, the path starts with a character other than "\\", and is relative to the key that is specified by the *RootObject* member.

### -field RootObject

Pointer to the registry key object that serves as the root for the path specified by the *CompleteName* member.

### -field ObjectType

The **ObjectType** member is reserved for internal use. Drivers must not access this member.

### -field CreateOptions

A bitwise OR of flags. For more information about these flags, see the *CreateOptions* parameter of the [ZwCreateKey](./nf-wdm-zwcreatekey.md) routine.

### -field Class

A pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that identifies the key's object class. For more information about this member, see the *Class* parameter of the [ZwCreateKey](./nf-wdm-zwcreatekey.md) routine.

### -field SecurityDescriptor

A pointer to a [**SECURITY_DESCRIPTOR**](../ntifs/ns-ntifs-_security_descriptor.md) structure that contains security information for the key object.

### -field SecurityQualityOfService

A pointer to a **SECURITY_QUALITY_OF_SERVICE** structure, which is defined in Winnt.h.

### -field DesiredAccess

The access mask that was specified by the thread that is attempting to create the registry key.

### -field GrantedAccess

An access mask that indicates the access rights that have been granted to the thread that is attempting to create the registry key. For more information about this member, see Remarks.

### -field Disposition

A value that indicates whether the registry key was created. For more information about this member, see the *Disposition* parameter of the [ZwCreateKey](./nf-wdm-zwcreatekey.md) routine and the following Remarks section.

### -field ResultObject

A pointer to a location that receives the address of the key object that represents the created registry key. For more information about this member, see Remarks.

### -field CallContext

Optional driver-defined context information that the driver's [RegistryCallback](./nc-wdm-ex_callback_function.md) routine can supply.

### -field RootObjectContext

A pointer to a driver-defined context information that the driver has associated with the root of the path for the registry object by calling [CmSetCallbackObjectContext](./nf-wdm-cmsetcallbackobjectcontext.md).

### -field Transaction

A pointer to a transaction object that the operation is attempted on. If this member is **NULL**, the operation is being performed in non-transactional context.

### -field Reserved

If this member is 1, then it is safe to cast this structure to type [REG_CREATE_KEY_INFORMATION_V1](./ns-wdm-_reg_create_key_information_v1.md), which contains additional parameters.

## -remarks

The configuration manager passes this structure to the [RegistryCallback](./nc-wdm-ex_callback_function.md) routine every time a thread attempts to create a key—for example, when a user-mode thread calls **RegCreateKey** or **RegCreateKeyEx** or when a driver calls [ZwCreateKey](./nf-wdm-zwcreatekey.md).

If the driver's *RegistryCallback* routine returns STATUS_CALLBACK_BYPASS for a **RegNtPreCreateKeyEx** notification, the driver must supply the **GrantedAccess**, **Disposition**, and **ResultObject** values.

For more information about registry filtering operations, see [Filtering Registry Calls](/windows-hardware/drivers/kernel/filtering-registry-calls).

## -see-also

[**REG_CREATE_KEY_INFORMATION_V1**](./ns-wdm-_reg_create_key_information_v1.md)

[**REG_POST_OPERATION_INFORMATION**](./ns-wdm-_reg_post_operation_information.md)

[RegistryCallback](./nc-wdm-ex_callback_function.md)

[SECURITY_DESCRIPTOR](../ntifs/ns-ntifs-_security_descriptor.md)

[UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[ZwCreateKey](./nf-wdm-zwcreatekey.md)