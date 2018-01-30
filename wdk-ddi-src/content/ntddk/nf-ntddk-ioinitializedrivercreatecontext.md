---
UID: NF:ntddk.IoInitializeDriverCreateContext
title: IoInitializeDriverCreateContext function
author: windows-driver-content
description: The IoInitializeDriverCreateContext routine initializes a caller-allocated variable of type IO_DRIVER_CREATE_CONTEXT.
old-location: ifsk\ioinitializedrivercreatecontext.htm
old-project: ifsk
ms.assetid: 1d35ed3e-d14f-43ad-9c11-38aa37e76492
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ioref_d9c833b9-0246-49b7-83c5-ef02ef562e17.xml, ifsk.ioinitializedrivercreatecontext, IoInitializeDriverCreateContext, ntddk/IoInitializeDriverCreateContext, IoInitializeDriverCreateContext routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	IoInitializeDriverCreateContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoInitializeDriverCreateContext function


## -description


The <b>IoInitializeDriverCreateContext</b> routine initializes a caller-allocated variable of type <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a>.


## -syntax


````
VOID IoInitializeDriverCreateContext(
   PIO_DRIVER_CREATE_CONTEXT DriverContext
);
````


## -parameters




### -param DriverContext

A pointer to a caller-allocated variable of type IO_DRIVER_CREATE_CONTEXT.


## -returns


None



## -remarks


The <b>IoInitializeDriverCreateContext</b> routine initializes a caller-allocated IO_DRIVER_CREATE_CONTEXT structure used in passing additional create parameters to the <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> and <a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a> routines.

Callers of <b>IoInitializeDriverCreateContext</b> can be running at any IRQL if the <i>DriverContext</i> block is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

Starting in Windows 10, version 1607, this routine sets the <b>SiloContext</b> member of <a href="..\ntddk\ns-ntddk-_io_driver_create_context.md">IO_DRIVER_CREATE_CONTEXT</a> to <b>IO_USE_AMBIENT_SILO</b>.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoInitializeDriverCreateContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

