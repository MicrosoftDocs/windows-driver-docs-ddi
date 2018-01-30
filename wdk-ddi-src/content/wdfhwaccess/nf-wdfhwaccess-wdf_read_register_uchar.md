---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_UCHAR
title: WDF_READ_REGISTER_UCHAR function
author: windows-driver-content
description: The WDF_READ_REGISTER_UCHAR function reads a byte from the specified register address.
old-location: wdf\wdf_read_register_uchar.htm
old-project: wdf
ms.assetid: C8633689-0900-42BB-9D0D-6F95CBA13A37
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_READ_REGISTER_UCHAR function, WDF_READ_REGISTER_UCHAR, wdfhwaccess/WDF_READ_REGISTER_UCHAR, wdf.wdf_read_register_uchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
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
-	Wdfhwaccess.h
apiname:
-	WDF_READ_REGISTER_UCHAR
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_READ_REGISTER_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_UCHAR</b> function reads a byte from the specified register address.


## -syntax


````
UCHAR WDF_READ_REGISTER_UCHAR(
  _In_ WDFDEVICE Device,
  _In_ PUCHAR    Register
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns


<b>WDF_READ_REGISTER_UCHAR</b> returns the byte that is read from the specified port address.


