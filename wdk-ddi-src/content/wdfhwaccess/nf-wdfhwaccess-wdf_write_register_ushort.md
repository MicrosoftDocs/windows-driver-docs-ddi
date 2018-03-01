---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_USHORT
title: WDF_WRITE_REGISTER_USHORT function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address.
old-location: wdf\wdf_write_register_ushort.htm
old-project: wdf
ms.assetid: E098794F-9A32-409E-9B44-04FDCEF75341
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_WRITE_REGISTER_USHORT, WDF_WRITE_REGISTER_USHORT function, wdf.wdf_write_register_ushort, wdfhwaccess/WDF_WRITE_REGISTER_USHORT
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
-	WDF_WRITE_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_WRITE_REGISTER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_REGISTER_USHORT</b> routine writes a USHORT value to the specified address.


## -syntax


````
void WDF_WRITE_REGISTER_USHORT(
  _In_ WDFDEVICE Device,
  _In_ PUSHORT   Register,
  _In_ ULONG     Value
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


### -param Value [in]

Specifies a USHORT value to write to the register.


## -returns



This function does not return a value.



