---
UID: NF:storport.StorPortWriteRegisterBufferUlong64
title: StorPortWriteRegisterBufferUlong64 macro
author: windows-driver-content
description: This StorPortWriteRegisterBufferUlong64 routine writes a number of ULONG64 values from a the specified 64-bit register address.
old-location: storage\storportwriteregisterbufferulong64.htm
old-project: storage
ms.assetid: 3C36DB8F-46C2-4E81-B2F3-6DE78D91566E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortWriteRegisterBufferUlong64, StorPortWriteRegisterBufferUlong64 routine [Storage Devices], storage.storportwriteregisterbufferulong64, storport/StorPortWriteRegisterBufferUlong64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
-	storport.h
api_name:
-	StorPortWriteRegisterBufferUlong64
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWriteRegisterBufferUlong64 macro


## -description


This <b>StorPortWriteRegisterBufferUlong64</b> routine writes a number of <b>ULONG64</b> values from a the specified 64-bit register address.
 


## -syntax


````
 VOID StorPortWriteRegisterBufferUlong64(
  _In_ PULONG64  Register,
  _In_ PULONG64  Buffer,
  _In_ ULONG     Count
);
````


## -parameters




### -param h

TBD


### -param r

TBD


### -param b

TBD


### -param c

TBD






#### - Buffer [in]

Pointer to the buffer to write the <b>ULONG64</b> values from.


#### - Count [in]

Specifies the number of data values to write. Each data item has a size of <b>sizeof</b>(ULONG64). 


#### - Register [in]

Pointer to the register where the data is written to. The register must be a mapped range in memory space


## -remarks



The <b>StorPortWriteRegisterBufferUlong64</b> routine is only available on the 64-bit version of Windows.




## -see-also

<a href="..\storport\nf-storport-storportreadregisterbufferulong64.md">StorPortReadRegisterBufferUlong64</a>



 

 


