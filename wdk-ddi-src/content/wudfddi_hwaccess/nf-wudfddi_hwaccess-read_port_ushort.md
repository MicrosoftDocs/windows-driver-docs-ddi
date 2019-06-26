---
UID: NF:wudfddi_hwaccess.READ_PORT_USHORT
title: READ_PORT_USHORT function (wudfddi_hwaccess.h)
description: The READ_PORT_USHORT function reads a USHORT value from the specified port address.
old-location: wdf\read_port_ushort.htm
tech.root: wdf
ms.assetid: 522C2745-A758-4C58-9891-BD2A70DBE498
ms.date: 02/26/2018
ms.keywords: READ_PORT_USHORT, READ_PORT_USHORT function, umdf.read_port_ushort, wdf.read_port_ushort, wudfddi_hwaccess/READ_PORT_USHORT
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_hwaccess.h
api_name:
- READ_PORT_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# READ_PORT_USHORT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_PORT_USHORT</b>  function reads a USHORT value from the specified port address.


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


## -returns



<b>READ_PORT_USHORT</b> returns the USHORT value that is read from the specified port address.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



