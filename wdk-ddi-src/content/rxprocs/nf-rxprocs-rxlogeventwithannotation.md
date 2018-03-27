---
UID: NF:rxprocs.RxLogEventWithAnnotation
title: RxLogEventWithAnnotation function
author: windows-driver-content
description: RxLogEventWithAnnotation allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.
old-location: ifsk\rxlogeventwithannotation.htm
old-project: ifsk
ms.assetid: cb8b757a-cff5-41cf-8155-2c45a8a35f00
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxLogEventWithAnnotation, RxLogEventWithAnnotation function [Installable File System Drivers], ifsk.rxlogeventwithannotation, rxprocs/RxLogEventWithAnnotation, rxref_9c7d3613-cf3b-4de9-bfcb-a1dbe9213834.xml
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
-	RxLogEventWithAnnotation
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxLogEventWithAnnotation function


## -description


<b>RxLogEventWithAnnotation</b> allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log.


## -parameters




### -param DeviceObject [in]

A pointer to the RDBSS device object.


### -param EventId

TBD


### -param Status

TBD


### -param DataBuffer

TBD


### -param DataBufferLength

TBD


### -param Annotation

TBD


### -param AnnotationCount [in]

The count of the number of annotation strings to add to the I/O error log structure.


#### - Annotations [in]

A pointer to any annotation strings to add to the I/O error log structure.


#### - Id [in]

The value indicating the I/O error log code which is different than an NTSTATUS value returned by a routine. The legal I/O error log code values are defined in the <i>ntiolog.h</i> header file included with the Microsoft Windows SDK and Visual Studio. 


#### - NtStatus [in]

The value indicating the status code of a routine indicating a failure.


#### - RawDataBuffer [in]

A pointer to a raw data buffer to be added to the I/O error log structure.


#### - RawDataLength [in]

The length of the raw data buffer to be added to the I/O error log structure.


## -returns



None




## -remarks



A network mini-redirector would call <b>RxLogEventWithAnnotation</b> to log an I/O error.

The I/O error log entry size is limited to a length of 255 characters. So if the combined length of the <i>Id</i>, <i>RawDataBuffer</i>, and <i>Annotations</i> parameters plus the size of the fixed part of the I/O error log entry exceeds 255, then <b>RxLogEventWithAnnotation</b> will silently fail and no I/O error log entry will be created.

The <b>RxLogEventWithAnnotation</b> routine needs to allocate memory in order to create the I/O error log entry . Consequently, <b>RxLogEventWithAnnotation</b> can silently fail if the memory allocation fails. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554515">RxLogEventDirect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554524">RxLogEventWithBufferDirect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557368">_RxLog</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxLogEventWithAnnotation function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

