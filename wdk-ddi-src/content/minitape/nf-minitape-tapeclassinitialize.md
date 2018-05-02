---
UID: NF:minitape.TapeClassInitialize
title: TapeClassInitialize function
author: windows-driver-content
description: The TapeClassInitialize routine performs much of the driver and device initialization on behalf of a miniclass driver.
old-location: storage\tapeclassinitialize.htm
old-project: storage
ms.assetid: f1c70ca5-2caf-4758-99bb-221af0a79211
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: TapeClassInitialize, TapeClassInitialize routine [Storage Devices], minitape/TapeClassInitialize, storage.tapeclassinitialize, tapeclas_92bf66d9-2a7b-4853-ad25-b6f854533a4e.xml
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
-	TapeClassInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# TapeClassInitialize function


## -description


The <b>TapeClassInitialize</b> routine performs much of the driver and device initialization on behalf of a miniclass driver. <b>TapeClassInitialize</b> loads the tape class driver entry points for tape I/O requests into the miniclass driver data structure, locates and claims unclaimed tape devices that the miniclass driver supports, and allocates and initializes the operating system resources for the miniclass driver and its devices. <b>TapeClassInitialize</b> uses miniclass-driver-specific information supplied in <i>TapeInitData</i> and calls back to the tape miniclass driver for driver-specific operations.


## -parameters




### -param Argument1 [in]

Pointer to driver context information that was passed to the tape miniclass driver's <b>DriverEntry</b> routine. The format of the information is operating system-specific and must not be interpreted by a tape miniclass driver.


### -param Argument2 [in]

Pointer to the second driver context structure that was passed to the tape miniclass driver's<b> DriverEntry</b> routine. The format of the information is operating system-specific and must not be interpreted by a tape miniclass driver.


### -param TapeInitData [in]

Pointer to a TAPE_INIT_DATA_EX structure containing driver-specific information such as the entry points for the tape miniclass driver's command processing routines.


## -returns



<b>TapeClassInitialize</b> returns a value indicating the success or failure of the driver initialization. The tape miniclass driver passes this value, uninterpreted, as the return value from its <b>DriverEntry</b> routine.




## -remarks



A tape miniclass driver calls <b>TapeClassInitialize</b> from its <b>DriverEntry</b> routine and passes driver-specific information in <i>TapeInitData</i>. <b>TapeClassInitialize</b> performs a large part of the driver initialization on behalf of the miniclass driver and insulates the miniclass driver from operating system-specific details.

<b>TapeClassInitialize</b> calls the tape miniclass driver for driver-specific activities required during initialization. For example, <b>TapeClassInitialize</b> calls the tape miniclass driver's TapeMiniVerifyInquiry routine to determine whether the driver supports a given tape device. <b>TapeClassInitialize</b> also calls the tape miniclass driver's TapeMiniExtensionInit routine to initialize the minitape extension, if the miniclass driver requested one.

A tape miniclass driver allocates a TAPE_INIT_DATA_EX structure on the stack, clears it with <b>TapeClassZeroMemory</b>, fills in all the appropriate members, and passes it to <b>TapeClassInitialize</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552656">DriverEntry of Tape Miniclass Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567968">TAPE_INIT_DATA_EX</a>
 

 

