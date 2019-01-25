---
UID: NF:minitape.TapeDebugPrint
title: TapeDebugPrint function (minitape.h)
description: The TapeDebugPrint routine prints the indicated string.
old-location: storage\tapedebugprint.htm
tech.root: storage
ms.assetid: d06e4308-f1a9-4acd-bc25-b3fd53129064
ms.date: 03/29/2018
ms.keywords: TapeDebugPrint, TapeDebugPrint routine [Storage Devices], minitape/TapeDebugPrint, storage.tapedebugprint, tapeclas_cc0c28ed-17e9-40cf-bf04-e906aa4f74f0.xml
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
-	TapeDebugPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# TapeDebugPrint function


## -description


The <b>TapeDebugPrint</b> routine prints the indicated string.


## -parameters




### -param DebugPrintLevel

Determines whether the string is printed or not. If this parameter has a value less than or equal to the tape class global variable <b>TapeClassDebug</b>, <b>TapeDebugPrint</b> prints the message, otherwise nothing is printed. If this parameter has a value of zero, <b>TapeClassDebug</b> always prints the message. 


### -param DebugMessage

Pointer to the string to be printed.


### -param param

TBD




## -returns



None



