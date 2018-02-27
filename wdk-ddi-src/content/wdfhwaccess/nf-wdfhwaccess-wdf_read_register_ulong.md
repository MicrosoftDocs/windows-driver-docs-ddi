---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_ULONG
title: WDF_READ_REGISTER_ULONG function
author: windows-driver-content
description: The WDF_READ_REGISTER_ULONG function reads a ULONG value from the specified register address.
old-location: wdf\wdf_read_register_ulong.htm
old-project: wdf
ms.assetid: 75EBA58B-4EE9-4D7D-A653-93E5E35569BB
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_READ_REGISTER_ULONG, WDF_READ_REGISTER_ULONG function, wdf.wdf_read_register_ulong, wdfhwaccess/WDF_READ_REGISTER_ULONG
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfhwaccess.h
api_name:
-	WDF_READ_REGISTER_ULONG
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_READ_REGISTER_ULONG function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_ULONG</b> function reads a ULONG value from the specified register address.


## -syntax


````
ULONG WDF_READ_REGISTER_ULONG(
  _In_ WDFDEVICE Device,
  _In_ PULONG    Register
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns



<b>WDF_READ_REGISTER_ULONG</b> returns the ULONG value that is read from the specified port address.



