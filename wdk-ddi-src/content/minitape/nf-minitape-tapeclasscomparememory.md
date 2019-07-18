---
UID: NF:minitape.TapeClassCompareMemory
title: TapeClassCompareMemory function (minitape.h)
description: The TapeClassCompareMemory routine compares two memory buffers and returns the number of bytes that are equivalent.
old-location: storage\tapeclasscomparememory.htm
tech.root: storage
ms.assetid: dfff350c-ff76-49d3-b4ba-a5a51fabd419
ms.date: 03/29/2018
ms.keywords: TapeClassCompareMemory, TapeClassCompareMemory routine [Storage Devices], minitape/TapeClassCompareMemory, storage.tapeclasscomparememory, tapeclas_77631fdd-b72a-4569-8066-54f260cb4d9a.xml
ms.topic: function
f1_keywords:
 - "minitape/TapeClassCompareMemory"
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Tape.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Tape.lib
- Tape.dll
api_name:
- TapeClassCompareMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# TapeClassCompareMemory function


## -description


The <b>TapeClassCompareMemory</b> routine compares two memory buffers and returns the number of bytes that are equivalent.


## -parameters




### -param Source1 [in, out]

Pointer to the first buffer to be compared.


### -param Source2 [in, out]

Pointer to the second buffer to be compared.


### -param Length [in]

Specifies the number of bytes to be compared.


## -returns



<b>TapeClassCompareMemory</b> returns the number of bytes that are equivalent.




## -remarks



A tape miniclass driver uses <b>TapeClassCompareMemory</b> to compare memory in a portable way. For example, a miniclass driver uses <b>TapeClassCompareMemory</b> in its TapeMiniVerifyInquiry routine to determine whether a given product ID matches one of the devices the driver supports.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nc-minitape-tape_verify_inquiry_routine">TapeMiniVerifyInquiry</a>
 

 

