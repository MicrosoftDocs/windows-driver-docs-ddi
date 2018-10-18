---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_UCHAR
title: WDF_READ_REGISTER_UCHAR function
author: windows-driver-content
description: The WDF_READ_REGISTER_UCHAR function reads a byte from the specified register address.
old-location: wdf\wdf_read_register_uchar.htm
tech.root: wdf
ms.assetid: C8633689-0900-42BB-9D0D-6F95CBA13A37
ms.date: 02/26/2018
ms.keywords: WDF_READ_REGISTER_UCHAR, WDF_READ_REGISTER_UCHAR function, wdf.wdf_read_register_uchar, wdfhwaccess/WDF_READ_REGISTER_UCHAR
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
-	WDF_READ_REGISTER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_READ_REGISTER_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_READ_REGISTER_UCHAR</b> function reads a byte from the specified register address.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register address, which must be a mapped range in memory space.


## -returns



<b>WDF_READ_REGISTER_UCHAR</b> returns the byte that is read from the specified port address.



