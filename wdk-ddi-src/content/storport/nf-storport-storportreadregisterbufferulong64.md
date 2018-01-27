---
UID: NF:storport.StorPortReadRegisterBufferUlong64
title: StorPortReadRegisterBufferUlong64 macro
author: windows-driver-content
description: This StorPortReadRegisterBufferUlong64 routine reads a number of ULONG64 values from the specified 64-bit register address into a buffer.
old-location: storage\storportreadregisterbufferulong64.htm
old-project: storage
ms.assetid: 585EE323-99EC-4367-8D97-CB554D695C11
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortReadRegisterBufferUlong64, StorPortReadRegisterBufferUlong64 routine [Storage Devices], StorPortReadRegisterBufferUlong64, storage.storportreadregisterbufferulong64
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
req.lib: storport.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	storport.h
apiname: 
-	StorPortReadRegisterBufferUlong64
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortReadRegisterBufferUlong64 macro


## -description


This <b>StorPortReadRegisterBufferUlong64</b> routine reads a number of <b>ULONG64</b> values from the specified 64-bit register address into a buffer.
 


## -syntax


````
 VOID StorPortReadRegisterBufferUlong64(
  _In_  PULONG64  Register,
  _Out_ PULONG64  Buffer,
  _In_  ULONG     Count
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




#### - Count [in]

Specifies the number of data values to read. Each data item has a size of <b>sizeof</b>(ULONG64). 


#### - Register [in]

Pointer to the register where the data is to be read. The register must be a mapped range in memory space


#### - Buffer [out]

Pointer to the buffer that receives the data that is read.


## -remarks


The <b>StorPortReadRegisterBufferUlong64</b> routine is only available on the 64-bit version of Windows.



## -see-also

<a href="..\storport\nf-storport-storportwriteregisterbufferulong64.md">StorPortWriteRegisterBufferUlong64</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterBufferUlong64 routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

