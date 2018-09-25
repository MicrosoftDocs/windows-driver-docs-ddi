---
UID: NF:minitape.TapeClassZeroMemory
title: TapeClassZeroMemory function
author: windows-driver-content
description: The TapeClassZeroMemory routine fills a buffer with zeros.
old-location: storage\tapeclasszeromemory.htm
tech.root: storage
ms.assetid: a1f15890-ded8-4aba-8b67-6f1fb1490178
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: TapeClassZeroMemory, TapeClassZeroMemory routine [Storage Devices], minitape/TapeClassZeroMemory, storage.tapeclasszeromemory, tapeclas_f48cbbef-af5f-4d1b-b79e-0982d4d09bde.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Tape.lib
-	Tape.dll
api_name:
-	TapeClassZeroMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# TapeClassZeroMemory function


## -description


The <b>TapeClassZeroMemory</b> routine fills a buffer with zeros.


## -parameters




### -param Buffer [in, out]

Pointer to the buffer that needs to be cleared.


### -param BufferSize [in]

Specifies the size of the buffer, in bytes.


## -returns



None




## -remarks



A tape miniclass driver calls <b>TapeClassZeroMemory</b> to zero a buffer in a portable way. A miniclass driver must use <b>TapeClassZeroMemory</b> to clear the TAPE_INIT_DATA_EX structure and CDBs before it uses them.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552656">DriverEntry of Tape Miniclass Driver</a>
 

 

