---
UID: NF:miniport.READ_REGISTER_ULONG64
title: READ_REGISTER_ULONG64 function (miniport.h)
description: The READ_REGISTER_ULONG64 function (miniport.h) reads a ULONG64 value from the specified register address.
tech.root: wdf
ms.date: 07/14/2022
keywords: ["READ_REGISTER_ULONG64 function"]
ms.keywords: READ_REGISTER_ULONG64, READ_REGISTER_ULONG64 function, umdf.read_register_ulong64, wdf.read_register_ulong64, wudfddi_hwaccess/READ_REGISTER_ULONG64
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
 - READ_REGISTER_ULONG64
 - miniport/READ_REGISTER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_hwaccess.h
api_name:
 - READ_REGISTER_ULONG64
---

## -description

> [!WARNING]
> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see [Getting Started with UMDF](/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2).]

The **READ_REGISTER_ULONG64** function reads a ULONG64 value from the specified register address.

## -parameters

### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.

## -returns

**READ_REGISTER_ULONG64** returns the ULONG64 value that is read from the specified port address.

## -remarks

For more information, see [Reading and Writing to Device Registers in UMDF 1.x Drivers](/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers).
