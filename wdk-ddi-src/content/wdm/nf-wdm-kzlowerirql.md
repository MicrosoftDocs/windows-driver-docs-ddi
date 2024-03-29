---
UID: NF:wdm.KzLowerIrql
title: KzLowerIrql function (wdm.h)
description: Restores the IRQL on the current processor to its original value.
tech.root: kernel
ms.date: 09/30/2018
keywords: ["KzLowerIrql function"]
ms.keywords: KzLowerIrql, KeLowerIrql
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: 
req.irql: HIGH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - KzLowerIrql
 - wdm/KzLowerIrql
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KzLowerIrql
---

# KzLowerIrql function


## -description

Restores the IRQL on the current processor to its original value. For information about IRQLs, see [Managing Hardware Priorities](/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -parameters

### -param NewIrql [in]

Specifies the IRQL that was returned from <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirql">KeRaiseIrql</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>.

## -remarks

This function is same as the [**KeLowerIrql**](nf-wdm-kelowerirql~r1.md) function.

## -see-also
