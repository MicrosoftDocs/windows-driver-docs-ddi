---
UID: NF:ntifs.SeAccessCheckFromStateEx
tech.root: ifsk
title: SeAccessCheckFromStateEx
ms.date: 01/10/2023
targetos: Windows
description: Learn more about the SeAccessCheckFromStateEx function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - SeAccessCheckFromStateEx
f1_keywords:
 - SeAccessCheckFromStateEx
 - ntifs/SeAccessCheckFromStateEx
dev_langs:
 - c++
helpviewer_keywords:
 - SeAccessCheckFromStateEx
---

## -description

**SeAccessCheckFromStateEx** checks whether the requested access rights can be granted to an object that is protected by a security descriptor and an optional object owner.

## -parameters

### -param SecurityDescriptor

[in] Pointer to a [**SECURITY_DESCRIPTOR**](ns-ntifs-_security_descriptor.md) structure containing the security information protecting the object being accessed.

### -param PrimaryToken

[in] Pointer to an opaque [ACCESS_TOKEN](/windows/win32/secauthz/access-tokens) structure for the primary token. This structure provides the token's information needed to perform an access check.

### -param ClientToken

[in_opt] Optional pointer to an opaque ACCESS_TOKEN structure for the client token.

### -param DesiredAccess

[in] An [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) value that specifies the desired access rights to check.

### -param PreviouslyGrantedAccess

[in] An [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) value that specifies any accesses that the user has already been granted; for example, as a result of holding a privilege.

### -param Privileges

[out] Pointer to a [**PRIVILEGE_SET**](../wdm/ns-wdm-_privilege_set.md) structure in which a privilege set is returned to indicate any privileges that were used as part of the access validation.

### -param GenericMapping

[in] Pointer to the [**GENERIC_MAPPING**](../wdm/ns-wdm-_generic_mapping.md) structure associated with this object type.

### -param AccessMode

[in] A KPROCESSOR_MODE value that specifies the processor mode to be used in the check. **AccessMode** can be either **KernelMode** or **UserMode**. Lower-level drivers should specify **KernelMode**.

### -param GrantedAccess

[out] Pointer to a returned [**ACCESS_MASK**](/windows-hardware/drivers/kernel/access-mask) value that indicates the granted access.

### -param AccessStatus

[out] Pointer to an NT status value that can be returned to indicate why access was denied. See Remarks.

## -returns

**SeAccessCheckFromStateEx** returns TRUE if access is allowed; it returns FALSE if access is not allowed.

## -remarks

**SeAccessCheckFromStateEx** might perform tests for the following privileges, depending on the accesses being requested:

* **SeTakeOwnershipPrivilege**
* **SeSecurityPrivilege**

This routine also might check whether the caller is the owner of the object in order to grant WRITE_DAC or READ_CONTROL access.

If this routine returns FALSE, the caller should use the returned **AccessStatus** as its return value. That is, the caller should avoid hardcoding a return value of STATUS_ACCESS_DENIED or any other specific STATUS_*XXX* value.

This routine might be called from DPC level so must not be pageable.

## -see-also

[**SeAccessCheck**](../wdm/nf-wdm-seaccesscheck.md)

[**SeAccessCheckFromState**](nf-ntifs-seaccesscheckfromstate.md)
