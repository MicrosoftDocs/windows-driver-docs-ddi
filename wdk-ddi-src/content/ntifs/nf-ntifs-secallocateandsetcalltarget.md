---
UID: NF:ntifs.SecAllocateAndSetCallTarget
tech.root: ifsk
title: SecAllocateAndSetCallTarget
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the SecAllocateAndSetCallTarget function.
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
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SecAllocateAndSetCallTarget
f1_keywords:
 - SecAllocateAndSetCallTarget
 - ntifs/SecAllocateAndSetCallTarget
dev_langs:
 - c++
helpviewer_keywords:
 - SecAllocateAndSetCallTarget
---

## -description

The **SecAllocateAndSetCallTarget** function allocates resources and sets a call target based on an IP address and an optional target name.

## -parameters

### -param lpIpAddress

[in, optional] A pointer to a buffer containing the IP address of the target. This parameter can be NULL if only the target name is provided.

### -param cchIpAddress

[in] The size, in bytes, of the IP address buffer.

### -param TargetName

[in, optional] A pointer to a wide string representing the canonical name of the target. This can be used to determine the nature of the resource.  

### -param FreeCallContext

[out] Pointer to an integer that indicates whether the call context should be freed. This value is equivalent to a Boolean value, where a non-zero value (TRUE) indicates that the caller is responsible for freeing the context by calling [**SecFreeCallContext**](nf-ntifs-secfreecallcontext.md).

## -returns

**SecAllocateAndSetCallTarget** returns SEC_E_OK if the operation is successful. Otherwise, it returns an error code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| SEC_E_INVALID_PARAMETER | One or more parameters are invalid. |
| SEC_E_INSUFFICIENT_MEMORY | There is not enough memory to complete the operation. |

## -remarks

**SecAllocateAndSetCallTarget** is primarily used to determine if a target is a private or enterprise resource, facilitating Single Sign-On (SSO) operations.

It allows both an IP address and a target name to be specified, providing flexibility in identifying the target resource. One of **lpIpAddress** or **TargetName** must be provided; otherwise, the function will return SEC_E_INVALID_PARAMETER.

## -see-also

[**SecAllocateAndSetIPAddress**](nf-ntifs-secallocateandsetipaddress.md)

[**SecFreeCallContext**](nf-ntifs-secfreecallcontext.md)
