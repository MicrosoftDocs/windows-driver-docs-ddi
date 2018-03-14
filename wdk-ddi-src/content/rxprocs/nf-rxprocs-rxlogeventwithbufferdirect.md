---
UID: NF:rxprocs.RxLogEventWithBufferDirect
title: RxLogEventWithBufferDirect function
author: windows-driver-content
description: RxLogEventWithBufferDirect allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.
old-location: ifsk\rxlogeventwithbufferdirect.htm
old-project: ifsk
ms.assetid: 09a7d452-efa1-4846-8077-1f6ce60515e7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxLogEventWithBufferDirect, RxLogEventWithBufferDirect function [Installable File System Drivers], ifsk.rxlogeventwithbufferdirect, rxprocs/RxLogEventWithBufferDirect, rxref_95cd6139-10e2-4cf1-bfd9-51b3d6dd1119.xml
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
-	RxLogEventWithBufferDirect
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxLogEventWithBufferDirect function


## -description


<b>RxLogEventWithBufferDirect</b> allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.


## -syntax


````
VOID RxLogEventWithBufferDirect(
  _In_ PVOID           DeviceObject,
  _In_ PUNICODE_STRING OriginatorId,
  _In_ ULONG           EventId,
  _In_ NTSTATUS        Status,
  _In_ PVOID           DataBuffer,
  _In_ USHORT          DataBufferLength,
  _In_ ULONG           LineNumber
);
````


## -parameters




### -param DeviceOrDriverObject

TBD


### -param OriginatorId [in]

The string indicating the caller generating the error.


### -param EventId [in]

The value indicating the I/O error log code which is different than an NTSTATUS value returned by a routine. The legal I/O error log code values are defined in the <i>ntiolog.h</i> header file included with the Microsoft Windows SDK and Visual Studio. 


### -param Status [in]

The value indicating the status code of a routine indicating a failure.


### -param DataBuffer [in]

A pointer to a data buffer to be added to the I/O error log structure.


### -param DataBufferLength [in]

The length of the data buffer to be added to the I/O error log structure.


### -param LineNumber [in]

The line number in the source code file where this failure occurred.


#### - DeviceObject [in]

A pointer to the RDBSS device object.


## -returns



None




## -remarks



<b>RxLogEventDirect</b> internally calls the <b>RxLogEventWithAnnotation</b> routine to create and write the log entry passing the <i>Status</i> and <i>LineNumber</i> parameters as the <i>Annotations</i> parameter to <b>RxLogEventWithAnnotation</b>. 

The I/O error log entry size is limited to a length of 255 characters. So if the combined length of the <i>EventId</i>, <i>DataBuffer</i>, and <i>Annotations</i> parameters plus the size of the fixed part of the I/O error log entry exceeds 255, then no I/O error log entry will be created.

The <b>RxLogEventWithAnnotation</b> routine needs to allocate memory in order to create the I/O error log entry . Consequently, <b>RxLogEventWithBufferDirect</b> can silently fail if the memory allocation fails. 




## -see-also

<a href="..\rxprocs\nf-rxprocs-rxlogeventdirect.md">RxLogEventDirect</a>



<a href="..\rxlog\nf-rxlog-_rxlog.md">_RxLog</a>



<a href="..\rxprocs\nf-rxprocs-rxlogeventwithannotation.md">RxLogEventWithAnnotation</a>



 

 


