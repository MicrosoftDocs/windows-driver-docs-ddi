---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_BUFFER_USHORT
title: WDF_READ_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WDF_READ_REGISTER_BUFFER_USHORT function reads a number of USHORT values from the specified register address into a buffer.
old-location: wdf\wdf_read_register_buffer_ushort.htm
old-project: wdf
ms.assetid: BA47B3D0-9515-40C6-B23D-A2D9FC993FB3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_READ_REGISTER_BUFFER_USHORT, WDF_READ_REGISTER_BUFFER_USHORT function, wdf.wdf_read_register_buffer_ushort, wdfhwaccess/WDF_READ_REGISTER_BUFFER_USHORT
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
req.lib: 
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
-	WDF_READ_REGISTER_BUFFER_USHORT
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_READ_REGISTER_BUFFER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_REGISTER_BUFFER_USHORT</b> function reads a number of USHORT values from the specified register address into a buffer.


## -syntax


````
void WDF_READ_REGISTER_BUFFER_USHORT(
  _In_  WDFDEVICE Device,
  _In_  PUSHORT   Register,
  _Out_ PUSHORT   Buffer,
  _In_  ULONG     Count 
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [out]

A pointer to a buffer into which an array of USHORT values is read.


### -param Count [in]

Specifies the number of USHORT values to be read into the buffer.


## -returns



This function does not return a value.



