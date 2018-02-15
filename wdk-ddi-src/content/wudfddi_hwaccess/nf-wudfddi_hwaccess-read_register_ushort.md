---
UID: NF:wudfddi_hwaccess.READ_REGISTER_USHORT
title: READ_REGISTER_USHORT function
author: windows-driver-content
description: The READ_REGISTER_USHORT function reads a USHORT value from the specified register address.
old-location: wdf\read_register_ushort.htm
old-project: wdf
ms.assetid: 75DDFC2A-EF7F-4652-B0D0-8BF1583B3679
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: READ_REGISTER_USHORT, READ_REGISTER_USHORT function, umdf.read_register_ushort, wdf.read_register_ushort, wudfddi_hwaccess/READ_REGISTER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_hwaccess.h
apiname:
-	READ_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: "*PUMDF_IO_TARGET_OPEN_PARAMS, UMDF_IO_TARGET_OPEN_PARAMS"
req.product: Windows 10 or later.
---

# READ_REGISTER_USHORT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_REGISTER_USHORT</b> function reads a USHORT value from the specified register address.


## -syntax


````
USHORT READ_REGISTER_USHORT(
  _In_ IWDFDevice3 *pDevice,
  _In_ PUSHORT     Register
);
````


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the device object of the device to access.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns



<b>READ_REGISTER_USHORT</b> returns the USHORT value that is read from the specified port address.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/A0640E60-B0DF-4CAD-B292-CC1875EF7F7D">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



