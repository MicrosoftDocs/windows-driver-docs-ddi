---
UID: NF:rxprocs.RxLogEventWithAnnotation
title: RxLogEventWithAnnotation function (rxprocs.h)
description: RxLogEventWithAnnotation allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.
old-location: ifsk\rxlogeventwithannotation.htm
tech.root: ifsk
ms.assetid: cb8b757a-cff5-41cf-8155-2c45a8a35f00
ms.date: 04/16/2018
ms.keywords: RxLogEventWithAnnotation, RxLogEventWithAnnotation function [Installable File System Drivers], ifsk.rxlogeventwithannotation, rxprocs/RxLogEventWithAnnotation, rxref_9c7d3613-cf3b-4de9-bfcb-a1dbe9213834.xml
ms.topic: function
f1_keywords:
 - "rxprocs/RxLogEventWithAnnotation"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxLogEventWithAnnotation
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxLogEventWithAnnotation function


## -description


<b>RxLogEventWithAnnotation</b> allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.


## -parameters




### -param DeviceObject [in]

A pointer to the RDBSS device object.


### -param EventId

<p>The value indicating the I/O error log code which is different than an NTSTATUS value returned by a routine. The legal I/O error log code values are defined in the <i>ntiolog.h</i> header file included with the Microsoft Windows SDK and Visual Studio. </p>


### -param Status

<p>The value indicating the status code of a routine indicating a failure.</p>


### -param DataBuffer

<p>A pointer to a raw data buffer to be added to the I/O error log structure.</p>


### -param DataBufferLength

<p>The length of the raw data buffer to be added to the I/O error log structure.</p>


### -param Annotation

<p>A pointer to any annotation strings to add to the I/O error log structure.</p>


### -param AnnotationCount [in]

The count of the number of annotation strings to add to the I/O error log structure.


## -returns



None




## -remarks



A network mini-redirector would call <b>RxLogEventWithAnnotation</b> to log an I/O error.

The I/O error log entry size is limited to a length of 255 characters. So if the combined length of the <i>Id</i>, <i>RawDataBuffer</i>, and <i>Annotations</i> parameters plus the size of the fixed part of the I/O error log entry exceeds 255, then <b>RxLogEventWithAnnotation</b> will silently fail and no I/O error log entry will be created.

The <b>RxLogEventWithAnnotation</b> routine needs to allocate memory in order to create the I/O error log entry . Consequently, <b>RxLogEventWithAnnotation</b> can silently fail if the memory allocation fails. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxprocs/nf-rxprocs-rxlogeventdirect">RxLogEventDirect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxprocs/nf-rxprocs-rxlogeventwithbufferdirect">RxLogEventWithBufferDirect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxlog/nf-rxlog-_rxlog">_RxLog</a>
 

 

