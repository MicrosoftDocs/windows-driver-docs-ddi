---
UID: NF:dbgeng.DebugCommandException
title: DebugCommandException function
author: windows-driver-content
description: Specifies a debug command exception.
old-location: debugger\debugcommandexception.htm
old-project: debugger
ms.assetid: 6DC67840-B985-45D0-8E81-671C3DC1EBC2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: DebugCommandException, DebugCommandException function [Windows Debugging], debugger.debugcommandexception, dbgeng/DebugCommandException
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dbgeng.h
apiname:
-	DebugCommandException
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# DebugCommandException function


## -description


Specifies a debug command exception.


## -syntax


````
void WINAPI DebugCommandException(
   ULONG Command,
   ULONG ArgSize,
   PVOID Arg
);
````


## -parameters




### -param Command

A command.


### -param ArgSize

The size of the argument.


### -param Arg

A pointer to an argument.


## -returns


This function does not return a value.


