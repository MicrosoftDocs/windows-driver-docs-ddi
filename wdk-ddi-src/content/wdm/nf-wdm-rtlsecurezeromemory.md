---
UID: NF:wdm.RtlSecureZeroMemory
tech.root: kernel
title: RtlSecureZeroMemory function (wdm.h)
ms.date: 07/14/2025
targetos: Windows
description: The RtlSecureZeroMemory routine securely fills a block of memory with zeros in a way that is guaranteed not to be optimized away by the compiler.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: Any level (see Remarks section)
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlSecureZeroMemory
f1_keywords:
 - RtlSecureZeroMemory
 - wdm/RtlSecureZeroMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlSecureZeroMemory
---

## -description

The **RtlSecureZeroMemory** routine securely fills a block of memory with zeros in a way that is guaranteed not to be optimized away by the compiler.

## -parameters

### -param Ptr [in, out]

A pointer to the memory block to be securely filled with zeros.

### -param cnt [in]

The number of bytes to fill with zeros.

## -returns

**RtlSecureZeroMemory** returns a pointer to the memory block that was filled (*Ptr*).

## -syntax

```cpp
PVOID RtlSecureZeroMemory(
  [in, out] PVOID  Ptr,
  [in]      SIZE_T cnt
);
```

## -remarks

- The function uses volatile memory accesses to ensure that the compiler cannot optimize away the zeroing operation, even if the memory appears to be unused after the call.

- This differs from [**RtlZeroMemory**](nf-wdm-rtlzeromemory.md), which may be optimized away by the compiler if the memory is not accessed again.

- The function guarantees that all specified bytes will be set to zero and that this operation will not be removed by compiler optimizations.

Callers of **RtlSecureZeroMemory** can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

### Example

```cpp
UCHAR SensitiveData[256];
UCHAR CryptographicKey[32];

// Use sensitive data
ProcessSensitiveInformation(SensitiveData);
PerformCryptographicOperation(CryptographicKey);

// Securely clear sensitive data from memory
// This will not be optimized away by the compiler
RtlSecureZeroMemory(SensitiveData, sizeof(SensitiveData));
RtlSecureZeroMemory(CryptographicKey, sizeof(CryptographicKey));
```

## -see-also

[**RtlZeroMemory**](nf-wdm-rtlzeromemory.md)

[**RtlFillVolatileMemory**](nf-wdm-rtlfillvolatilememory.md)

[**RtlSetVolatileMemory**](nf-wdm-rtlsetvolatilememory.md)
