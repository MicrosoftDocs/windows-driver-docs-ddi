---
UID: NF:ntddk.RtlNormalizeSecurityDescriptor
title: RtlNormalizeSecurityDescriptor function
description: TBD
tech.root: kernel
ms.date: 03/24/2020
ms.topic: function
ms.keywords: RtlNormalizeSecurityDescriptor
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: APC_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNormalizeSecurityDescriptor
product:
 - Windows
f1_keywords:
 - RtlNormalizeSecurityDescriptor
 - ntddk/RtlNormalizeSecurityDescriptor
---

# RtlNormalizeSecurityDescriptor function


## -description

This routine examines a security descriptor for ways to modify its layout, with the goal that any two equivalent security descriptors should be able to be single instanced in $SDS as often as possible, and a secondary goal that the stored security descriptor should be as small as possible.

## -parameters

### -param SecurityDescriptor

Pointer to a pointer to the SECURITY_DESCRIPTOR to normalize. The security descriptor must be in self-relative format.  If **NewSecurityDescriptor** is not provided, this location may be updated with a newly allocated security descriptor from paged pool (freeing the original security descriptor) if modifications were made.

### -param SecurityDescriptorLength

Length in bytes of the security descriptor to normalize.

### -param NewSecurityDescriptor

If present and points to NULL, receives a pointer to a newly allocated security descriptor from paged pool if modications were made, instead of updating **SecurityDescriptor**.

If present and points to non-NULL, a modified security descriptor is instead constructed directly in the buffer (assumed to be at least of length **SecurityDescriptorLength**) provided by the caller.

### -param NewSecurityDescriptorLength

Optionally receives the length in bytes of the modified security descriptor if this routine makes modifications.

### -param CheckOnly

A BOOLEAN value that if TRUE specifies that the routine should take no action when modifications would otherwise be made. In this case, a modified security descriptor is not created.

## -returns

Returns TRUE if modifications were made or would have been made and FALSE otherwise (including failure).

## -remarks

If this routine makes any modifications, it returns the modified security descriptor unless the caller specifies CheckOnly indicating that they only want to know if modifications would be made.

The transformations currently supported are:

* Arrange the sections in the order Sacl => Dacl => Owner => Group.
* Eliminate unnecessary padding (beyond simple alignment) between sections.
* Zero any alignment bytes between sections.
* Eliminate any Sacl that contains no ACEs.
* Eliminate duplicate ALLOW ACEs in the Sacl and Dacl.

## -see-also

