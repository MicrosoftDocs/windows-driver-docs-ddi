---
UID: NF:miniport.WRITE_REGISTER_ULONG64
title: WRITE_REGISTER_ULONG64 function (miniport.h)
description: The WRITE_REGISTER_ULONG64 function (miniport.h) writes a ULONG64 value to the specified register address.
tech.root: wdf
ms.date: 07/14/2022
keywords: ["WRITE_REGISTER_ULONG64 function"]
ms.keywords: WRITE_REGISTER_ULONG64, WRITE_REGISTER_ULONG64 function, umdf.write_register_ulong64, wdf.write_register_ulong64, wudfddi_hwaccess/WRITE_REGISTER_ULONG64
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: 64-bit Windows
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
f1_keywords:
 - WRITE_REGISTER_ULONG64
 - miniport/WRITE_REGISTER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_hwaccess.h
api_name:
 - WRITE_REGISTER_ULONG64
---

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).]

The **WRITE_REGISTER_ULONG64** function writes a ULONG64 value to the specified address.

## -parameters

### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.

### -param Value [in]

Specifies a ULONG64 value to write to the register.

## -remarks

For more information, see [Reading and Writing to Device Registers in UMDF 1.x Drivers](/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers).
