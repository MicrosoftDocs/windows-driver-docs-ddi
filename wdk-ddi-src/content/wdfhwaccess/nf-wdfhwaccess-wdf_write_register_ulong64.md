---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_ULONG64
title: WDF_WRITE_REGISTER_ULONG64 function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address.
old-location: wdf\wdf_write_register_ulong64.htm
old-project: wdf
ms.assetid: 471B6165-24A0-45E1-AD7F-B7D3468DF573
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WDF_WRITE_REGISTER_ULONG64, WDF_WRITE_REGISTER_ULONG64 function, wdf.wdf_write_register_ulong64, wdfhwaccess/WDF_WRITE_REGISTER_ULONG64
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
-	WDF_WRITE_REGISTER_ULONG64
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_WRITE_REGISTER_ULONG64 function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_REGISTER_ULONG64</b> function writes a ULONG64 value to the specified address.


## -syntax


````
void WDF_WRITE_REGISTER_ULONG64(
  _In_ WDFDEVICE Device,
  _In_ PULONG64  Register,
  _In_ ULONG     Value
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Value [in]

Specifies a ULONG64 value to write to the register.


## -returns



This function does not return a value.



