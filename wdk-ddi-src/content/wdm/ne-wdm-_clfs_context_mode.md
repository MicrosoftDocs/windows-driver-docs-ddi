---
UID: NE:wdm._CLFS_CONTEXT_MODE
title: "_CLFS_CONTEXT_MODE"
author: windows-driver-content
description: The CLFS_CONTEXT_MODE enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream.
old-location: kernel\clfs_context_mode.htm
old-project: kernel
ms.assetid: 35f2b42d-d67f-4fd4-adde-918a2587980b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ClfsContextNone, ClfsContextUndoNext, CLFS_CONTEXT_MODE, kernel.clfs_context_mode, PPCLFS_CONTEXT_MODE enumeration pointer [Kernel-Mode Driver Architecture], *PCLFS_CONTEXT_MODE, ClfsContextForward, _CLFS_CONTEXT_MODE, PCLFS_CONTEXT_MODE, sysenum_b51a934c-9174-4607-8da9-22c7ecf56730.xml, wdm/PCLFS_CONTEXT_MODE, wdm/ClfsContextNone, PPCLFS_CONTEXT_MODE, wdm/ClfsContextPrevious, wdm/ClfsContextForward, wdm/ClfsContextUndoNext, PCLFS_CONTEXT_MODE enumeration pointer [Kernel-Mode Driver Architecture], wdm/PPCLFS_CONTEXT_MODE, CLFS_CONTEXT_MODE enumeration [Kernel-Mode Driver Architecture], ClfsContextPrevious, wdm/CLFS_CONTEXT_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CLFS_CONTEXT_MODE
product: Windows
targetos: Windows
req.typenames: CLFS_CONTEXT_MODE, *PCLFS_CONTEXT_MODE, PPCLFS_CONTEXT_MODE
req.product: Windows 10 or later.
---

# _CLFS_CONTEXT_MODE enumeration


## -description


The <b>CLFS_CONTEXT_MODE</b> enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream.


## -syntax


````
typedef enum _CLFS_CONTEXT_MODE { 
  ClfsContextNone      = 0,
  ClfsContextUndoNext  = 1,
  ClfsContextPrevious  = 2,
  ClfsContextForward   = 3
} CLFS_CONTEXT_MODE, *PCLFS_CONTEXT_MODE, **PPCLFS_CONTEXT_MODE;
````


## -enum-fields




### -field ClfsContextNone

Indicates that a variable of type <b>CLFS_CONTEXT_MODE</b> has not yet been assigned a meaningful value.


### -field ClfsContextUndoNext

Indicates that the next record in the sequence is pointed to by the <a href="https://msdn.microsoft.com/4637fa0c-2f19-4f0c-bf13-f4ccac2e7284">undo-next LSN</a> of the current record.


### -field ClfsContextPrevious

Indicates that the next record in the sequence is pointed to by the <a href="https://msdn.microsoft.com/4637fa0c-2f19-4f0c-bf13-f4ccac2e7284">previous LSN</a> of the current record.


### -field ClfsContextForward

Indicates that the next record in the sequence is the record in the stream that immediately follows the current record.


## -see-also

<a href="..\wdm\nf-wdm-clfsreadpreviousrestartarea.md">ClfsReadPreviousRestartArea</a>



<a href="..\wdm\nf-wdm-clfsreadnextlogrecord.md">ClfsReadNextLogRecord</a>



<a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>



<a href="..\wdm\nf-wdm-clfsreadlogrecord.md">ClfsReadLogRecord</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_CONTEXT_MODE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

