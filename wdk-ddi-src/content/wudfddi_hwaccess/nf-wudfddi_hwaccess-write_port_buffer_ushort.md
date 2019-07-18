---
UID: NF:wudfddi_hwaccess.WRITE_PORT_BUFFER_USHORT
title: WRITE_PORT_BUFFER_USHORT function (wudfddi_hwaccess.h)
description: The WRITE_PORT_BUFFER_USHORT function writes a number of USHORT values from a buffer to the specified port address.
old-location: wdf\write_port_buffer_ushort.htm
tech.root: wdf
ms.assetid: 04F51A7D-70D8-4844-973D-70B7A7797221
ms.date: 02/26/2018
ms.keywords: WRITE_PORT_BUFFER_USHORT, WRITE_PORT_BUFFER_USHORT function, umdf.write_port_buffer_ushort, wdf.write_port_buffer_ushort, wudfddi_hwaccess/WRITE_PORT_BUFFER_USHORT
ms.topic: function
f1_keywords:
 - "wudfddi_hwaccess/WRITE_PORT_BUFFER_USHORT"
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
- WRITE_PORT_BUFFER_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WRITE_PORT_BUFFER_USHORT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_PORT_BUFFER_USHORT</b> function writes a number of USHORT values from a buffer to the specified port address. 



## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.



### -param Buffer [in]

A pointer to a buffer from which an array of USHORT values is to be written.



### -param Count [in]

Specifies the number of USHORT values to be written to the buffer.


## -returns



This function does not return a value.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



