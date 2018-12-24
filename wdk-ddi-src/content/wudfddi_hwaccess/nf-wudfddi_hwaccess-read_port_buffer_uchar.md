---
UID: NF:wudfddi_hwaccess.READ_PORT_BUFFER_UCHAR
title: READ_PORT_BUFFER_UCHAR function
description: The READ_PORT_BUFFER_UCHAR function reads a number of bytes from the specified port address into a buffer.
old-location: wdf\read_port_buffer_uchar.htm
tech.root: wdf
ms.assetid: CDA0A86B-94E7-4825-9826-0E12ECF42B57
ms.date: 02/26/2018
ms.keywords: READ_PORT_BUFFER_UCHAR, READ_PORT_BUFFER_UCHAR function, umdf.read_port_buffer_uchar, wdf.read_port_buffer_uchar, wudfddi_hwaccess/READ_PORT_BUFFER_UCHAR
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_hwaccess.h
api_name:
-	READ_PORT_BUFFER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# READ_PORT_BUFFER_UCHAR function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_PORT_BUFFER_UCHAR</b> function reads a number of bytes from the specified port address into a buffer.


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a> interface for the device object of the device to access.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


### -param Buffer [out]

A pointer to a buffer into which an array of UCHAR values is read.


### -param Count [in]

Specifies the number of bytes to be read into the buffer.


## -returns



This function does not return a value.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



