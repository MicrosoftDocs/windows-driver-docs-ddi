---
UID: NF:wudfddi_hwaccess.WRITE_REGISTER_BUFFER_UCHAR
title: WRITE_REGISTER_BUFFER_UCHAR function (wudfddi_hwaccess.h)
description: The WRITE_REGISTER_BUFFER_UCHAR function writes a number of bytes from a buffer to the specified register.
old-location: wdf\write_register_buffer_uchar.htm
tech.root: wdf
ms.assetid: 5A124150-44E8-4F95-913A-8ECA29669A24
ms.date: 02/26/2018
keywords: ["WRITE_REGISTER_BUFFER_UCHAR function"]
ms.keywords: WRITE_REGISTER_BUFFER_UCHAR, WRITE_REGISTER_BUFFER_UCHAR function, umdf.write_register_buffer_uchar, wdf.write_register_buffer_uchar, wudfddi_hwaccess/WRITE_REGISTER_BUFFER_UCHAR
f1_keywords:
 - "wudfddi_hwaccess/WRITE_REGISTER_BUFFER_UCHAR"
 - "WRITE_REGISTER_BUFFER_UCHAR"
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_hwaccess.h
api_name:
- WRITE_REGISTER_BUFFER_UCHAR
targetos: Windows
req.typenames: 
---

# WRITE_REGISTER_BUFFER_UCHAR function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_BUFFER_UCHAR</b> function writes a number of bytes from a buffer to the specified register.


## -parameters




### -param pDevice 
[in]
Specifies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.


### -param Register 
[in]
A pointer to the register, which must be a mapped range in memory space.


### -param Buffer 
[in]
A pointer to a buffer from which an array of UCHAR values is to be written.


### -param Count 
[in]
Specifies the number of bytes to write to the register.


## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



