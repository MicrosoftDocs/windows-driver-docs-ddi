---
UID: NF:fltkernel.FltMupGetProviderInfoFromFileObject
tech.root: ifsk
title: FltMupGetProviderInfoFromFileObject
ms.date: 10/25/2024
targetos: Windows
description: Learn more about the FltMupGetProviderInfoFromFileObject function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
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
 - fltkernel.h
api_name:
 - FltMupGetProviderInfoFromFileObject
f1_keywords:
 - FltMupGetProviderInfoFromFileObject
 - fltkernel/FltMupGetProviderInfoFromFileObject
dev_langs:
 - c++
helpviewer_keywords:
 - FltMupGetProviderInfoFromFileObject
---

## -description

**FltMupGetProviderInfoFromFileObject** retrieves the provider information corresponding to a file object.

## -parameters

### -param Instance

[in] Opaque pointer to the filter instance associated with this file object. This parameter is required and can't be NULL.

### -param FileObject

[in] Pointer to the file object for which the provider information is to be retrieved. This parameter is required and can't be NULL.

### -param Level

[in] The level of information that this routine should return. For more information about the possible values for this parameter, see [**FsRtlMupGetProviderInfoFromFileObject**](../ntifs/nf-ntifs-fsrtlmupgetproviderinfofromfileobject.md).

### -param Buffer

[out] Pointer to a buffer that receives the provider information. The returned data is based on the specified **Level**. This buffer must be large enough to hold the information requested by the Level parameter.

### -param BufferSize

[in/out] Pointer to a variable that specifies the size, in bytes, of the buffer that is pointed to by the **Buffer** parameter. On input, this variable specifies the size of the buffer. On output, this variable receives the number of bytes that were written to the buffer.

## -returns

**FltMupGetProviderInfoFromFileObject** returns STATUS_SUCCESS if the operation is successful. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

This routine is needed to handle the case of providers that register using
[**FsRtlRegisterUncProviderEx**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex.md). The device name on the file objects for such provider would be *\Device\Mup*.

Filters can use this routine for the following purposes:

* To be able to filter specific redirectors.
* To find a redirector backing a file object so that they can work around possible bugs in redirectors.

The MUP (multiple UNC provider) can't be unloaded for this call.

The caller guarantees that the **FileObject** will be valid for the duration of the call.

## -see-also

[**FsRtlMupGetProviderInfoFromFileObject**](../ntifs/nf-ntifs-fsrtlmupgetproviderinfofromfileobject.md)

[**FsRtlRegisterUncProviderEx**](../ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex.md)
