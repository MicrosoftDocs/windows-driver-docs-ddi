---
UID: NS:fltkernel._FLT_CALLBACK_DATA_QUEUE
title: FLT_CALLBACK_DATA_QUEUE (fltkernel.h)
description: FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use FltCbdqInitialize to initialize this structure.
old-location: ifsk\flt_callback_data_queue.htm
tech.root: ifsk
ms.date: 08/11/2022
keywords: ["FLT_CALLBACK_DATA_QUEUE structure"]
ms.keywords: "*PFLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE structure [Installable File System Drivers], FltSystemStructures_d43817d6-bc53-407d-8a3f-c6268112eb6e.xml, PFLT_CALLBACK_DATA_QUEUE, PFLT_CALLBACK_DATA_QUEUE structure pointer [Installable File System Drivers], _FLT_CALLBACK_DATA_QUEUE, fltkernel/FLT_CALLBACK_DATA_QUEUE, fltkernel/PFLT_CALLBACK_DATA_QUEUE, ifsk.flt_callback_data_queue"
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FLT_CALLBACK_DATA_QUEUE, *PFLT_CALLBACK_DATA_QUEUE
f1_keywords:
 - _FLT_CALLBACK_DATA_QUEUE
 - fltkernel/_FLT_CALLBACK_DATA_QUEUE
 - PFLT_CALLBACK_DATA_QUEUE
 - fltkernel/PFLT_CALLBACK_DATA_QUEUE
 - FLT_CALLBACK_DATA_QUEUE
 - fltkernel/FLT_CALLBACK_DATA_QUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - _FLT_CALLBACK_DATA_QUEUE
 - PFLT_CALLBACK_DATA_QUEUE
 - FLT_CALLBACK_DATA_QUEUE
---

# FLT_CALLBACK_DATA_QUEUE structure

## -description

**FLT_CALLBACK_DATA_QUEUE** is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use [**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md) to initialize this structure.

## -struct-fields

### -field Csq

Do not set directly.

### -field Flags

Do not set directly.

### -field Instance

Do not set directly.

### -field InsertIo

Do not set directly.

### -field RemoveIo

Do not set directly.

### -field PeekNextIo

Do not set directly.

### -field Acquire

Do not set directly.

### -field Release

Do not set directly.

### -field CompleteCanceledIo

Do not set directly.

## -see-also

[**FltCbdqDisable**](nf-fltkernel-fltcbdqdisable.md)

[**FltCbdqEnable**](nf-fltkernel-fltcbdqenable.md)

[**FltCbdqInitialize**](nf-fltkernel-fltcbdqinitialize.md)

[**FltCbdqInsertIo**](nf-fltkernel-fltcbdqinsertio.md)

[**FltCbdqRemoveIo**](nf-fltkernel-fltcbdqremoveio.md)

[**FltCbdqRemoveNextIo**](nf-fltkernel-fltcbdqremovenextio.md)
