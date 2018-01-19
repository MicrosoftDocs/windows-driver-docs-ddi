---
UID: NF:minitape.TapeDebugPrint
title: TapeDebugPrint function
author: windows-driver-content
description: The TapeDebugPrint routine prints the indicated string.
old-location: storage\tapedebugprint.htm
old-project: storage
ms.assetid: d06e4308-f1a9-4acd-bc25-b3fd53129064
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: TapeDebugPrint
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
req.alt-api: TapeDebugPrint
req.alt-loc: Tape.lib,Tape.dll
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
req.typenames: TAPE_STATUS, *PTAPE_STATUS
---

# TapeDebugPrint function



## -description
The <b>TapeDebugPrint</b> routine prints the indicated string.



## -syntax

````
VOID TapeDebugPrint(
   ULONG  DebugPrintLevel,
   PCCHAR DebugMessage
);
````


## -parameters

### -param DebugPrintLevel 

Determines whether the string is printed or not. If this parameter has a value less than or equal to the tape class global variable <b>TapeClassDebug</b>, <b>TapeDebugPrint</b> prints the message, otherwise nothing is printed. If this parameter has a value of zero, <b>TapeClassDebug</b> always prints the message. 


### -param DebugMessage 

Pointer to the string to be printed.


## -returns
None


## -remarks
