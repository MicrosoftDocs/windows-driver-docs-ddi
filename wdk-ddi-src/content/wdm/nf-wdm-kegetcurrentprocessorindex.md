---
UID: NF:wdm.KeGetCurrentProcessorIndex
tech.root: kernel
title: KeGetCurrentProcessorIndex
ms.date: 10/23/2024
targetos: Windows
description: KeGetCurrentProcessorIndex returns the index of the processor that the caller is running on.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll:
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql:
req.kmdf-ver: 
req.lib:
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
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
 - wdm.h
api_name:
 - KeGetCurrentProcessorIndex
f1_keywords:
 - KeGetCurrentProcessorIndex
 - wdm/KeGetCurrentProcessorIndex
dev_langs:
 - c++
helpviewer_keywords:
 - KeGetCurrentProcessorIndex
---

## -description

KeGetCurrentProcessorIndex returns the index of the processor that the caller is running on.

## -returns

KeGetCurrentProcessorIndex returns the system wide index of the logical processor the caller is running on.

## -remarks

KeGetCurrentProcessorIndex is similar to KeGetCurrentProcessorNumber but rather than returning a PROCESSOR_NUMBER structure or a group relative index KeGetCurrentProcessorIndex behaves as if all the processors on the system were numbered 0..N-1 and returns a value between 0 and N-1 inclusive. The index is not guaranteed to be less than the result of KeQueryActiveProcessorCount but will be less than the result of KeQueryActiveProcessorCountEx(ALL_PROCESSOR_GROUPS).

## -see-also

[KeGetCurrentProcessorNumber](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kegetcurrentprocessornumber)

[KeGetCurrentProcessorNumberEx](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kegetcurrentprocessornumberex)

[KeQueryActiveProcessorCount](nf-wdm-kequeryactiveprocessorcount.md)

[KeQueryActiveProcessorCountEx](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactiveprocessorcountex)
