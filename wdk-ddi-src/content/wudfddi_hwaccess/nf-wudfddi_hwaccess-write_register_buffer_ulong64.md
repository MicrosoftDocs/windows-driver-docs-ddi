---
UID: NF:wudfddi_hwaccess.WRITE_REGISTER_BUFFER_ULONG64
title: WRITE_REGISTER_BUFFER_ULONG64 function
author: windows-driver-content
description: The WRITE_REGISTER_BUFFER_ULONG64 function writes a number of ULONG64 values from a buffer to the specified register.
old-location: wdf\write_register_buffer_ulong64.htm
old-project: wdf
ms.assetid: 18858A87-D7D8-4387-AD84-6717EC3DAC25
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WRITE_REGISTER_BUFFER_ULONG64, WRITE_REGISTER_BUFFER_ULONG64 function, umdf.write_register_buffer_ulong64, wdf.write_register_buffer_ulong64, wudfddi_hwaccess/WRITE_REGISTER_BUFFER_ULONG64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi_hwaccess.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_hwaccess.h
api_name:
-	WRITE_REGISTER_BUFFER_ULONG64
product:
- Windows
targetos: Windows
req.typenames: UMDF_IO_TARGET_OPEN_PARAMS, *PUMDF_IO_TARGET_OPEN_PARAMS
req.product: Windows 10 or later.
---

# WRITE_REGISTER_BUFFER_ULONG64 function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_BUFFER_ULONG64</b> function writes a number of ULONG64 values from a buffer to the specified register.


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a> interface for the device object of the device to access.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

A pointer to a buffer into which an array of ULONG64 values is to be written.


### -param Count [in]

Specifies the number of ULONG64 values to write to the register.


## -returns



This function does not return a value.




## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.

For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



