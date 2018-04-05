---
UID: NF:rxprocs.RxLogEventDirect
title: RxLogEventDirect function
author: windows-driver-content
description: RxLogEventDirect is called to log an error to the I/O error log. It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly.
old-location: ifsk\rxlogeventdirect.htm
old-project: ifsk
ms.assetid: fc0bf8c4-cc0b-4f1e-bd4e-facf8f0d2a96
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxLogEventDirect, RxLogEventDirect routine [Installable File System Drivers], ifsk.rxlogeventdirect, rxprocs/RxLogEventDirect, rxref_654ffecc-ea49-44b8-b454-9f66e9519ddd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h, Rxstruc.h
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxprocs.h
api_name:
-	RxLogEventDirect
product:
- Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxLogEventDirect function


## -description


<b>RxLogEventDirect</b> is called to log an error to the I/O error log. 

It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly.


## -parameters




### -param DeviceObject [in]

A pointer to the RDBSS device object.


### -param OriginatorId [in]

A string indicating the caller generating the error.


### -param EventId [in]

The value indicating the I/O error log code value which is different than an NTSTATUS value returned by a routine. The legal I/O error log code values are defined in the <i>ntiolog.h</i> header file included with the Microsoft Windows SDK and Visual Studio.


### -param Status [in]

The value indicating the status code of a routine indicating a failure.


### -param Line [in]

The line number in the source code file where this failure occurred.


## -returns



None




## -remarks



<b>RxLogEventDirect</b> internally calls the <b>RxLogEventWithAnnotation</b> routine to create and write the log entry. 

The I/O error log entry size is limited to a length of 255 characters. So if the combined length of the <i>OriginatorId</i> plus the size of the fixed part of the I/O error log exceeds 255, then no I/O error log entry will be created.

The <b>RxLogEventWithAnnotation</b> routine needs to allocate memory in order to create the I/O error log entry . Consequently, <b>RxLogEventDirect</b> can silently fail if the memory allocation fails. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554519">RxLogEventWithAnnotation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554524">RxLogEventWithBufferDirect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557368">_RxLog</a>
 

 

