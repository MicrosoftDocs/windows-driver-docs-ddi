---
UID: NF:ntifs.RtlQueryPackageIdentityEx
title: RtlQueryPackageIdentityEx function
author: windows-driver-content
description: RtlQueryPackageIdentityEx returns the associated full package name. It can optionally also return the package relative application name, and whether an application is considered packaged. 
tech.root: ifsk
ms.assetid: c4d1d0f4-1ca6-4f2b-91a0-8356a5d6cdde
ms.author: windowsdriverdev
ms.date: 10/30/2019
ms.topic: function
ms.keywords: RtlQueryPackageIdentityEx
req.header: ntifs.h
f1_keywords:
 - "ntifs/RtlQueryPackageIdentityEx"
req.include-header:
req.target-type:
req.target-min-winverclnt: Available on Windows 8.1 and later versions
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- RtlQueryPackageIdentityEx
product: 
- Windows
targetos: Windows

---

# RtlQueryPackageIdentityEx function

## -description

**RtlQueryPackageIdentityEx** returns the associated full package name. It can optionally also return the package relative application name, and whether an application is considered packaged.

## -parameters

### -param TokenObject

Handle to a token object (user mode) that was opened with TOKEN_QUERY access, or to a raw token object (kernel mode).

### -param PackageFullName

Pointer to a wide character buffer that will receive the unique package key. The buffer will be null terminated upon success.

### -param PackageSize

Pointer to the value that defines the size of the buffer that *PackageFullName* points to. On output, it will contain the written size including the terminating null.

### -param AppId

Pointer to a wide character buffer that may receive the package relative application identifier. *AppId* is optional and can be **NULL**.

### -param AppIdSize

Pointer to the value that defines the size of the buffer that *AppId* points to. On output, it will contain the written size including the terminating null. If **AppId** is not **NULL**, **AppIdSize** must point to a valid value; otherwise **AppIdSize** should set to **NULL**.

### -param DynamicId

Pointer to a value that receives a dynamic ID for the application. *DynamicId* is optional and can be **NULL**.

### -param Flags

Pointer to a value that receives a bitmask of values for the package attribute.

## -returns

**RtlQueryPackageIdentityEx** returns STATUS_SUCCESS upon successful completion; otherwise it returns a code such as one of the following.

| Error Code | Meaning |
| ---------- | ------- |
| STATUS_INVALID_PARAMETER | A parameter contains an invalid value; for example, a size value was not provided for a non-NULL buffer. This is an error code. |
| STATUS_NOT_FOUND | A package identity does not exist. |

## -remarks

## -see-also
