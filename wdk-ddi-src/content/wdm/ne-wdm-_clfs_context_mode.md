---
UID: NE:wdm._CLFS_CONTEXT_MODE
title: "_CLFS_CONTEXT_MODE" (wdm.h)
description: The CLFS_CONTEXT_MODE enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream.
old-location: kernel\clfs_context_mode.htm
tech.root: kernel
ms.assetid: 35f2b42d-d67f-4fd4-adde-918a2587980b
ms.date: 04/30/2018
ms.keywords: "*PCLFS_CONTEXT_MODE, CLFS_CONTEXT_MODE, CLFS_CONTEXT_MODE enumeration [Kernel-Mode Driver Architecture], ClfsContextForward, ClfsContextNone, ClfsContextPrevious, ClfsContextUndoNext, PCLFS_CONTEXT_MODE, PCLFS_CONTEXT_MODE enumeration pointer [Kernel-Mode Driver Architecture], PPCLFS_CONTEXT_MODE, PPCLFS_CONTEXT_MODE enumeration pointer [Kernel-Mode Driver Architecture], _CLFS_CONTEXT_MODE, kernel.clfs_context_mode, sysenum_b51a934c-9174-4607-8da9-22c7ecf56730.xml, wdm/CLFS_CONTEXT_MODE, wdm/ClfsContextForward, wdm/ClfsContextNone, wdm/ClfsContextPrevious, wdm/ClfsContextUndoNext, wdm/PCLFS_CONTEXT_MODE, wdm/PPCLFS_CONTEXT_MODE"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLFS_CONTEXT_MODE
product:
- Windows
targetos: Windows
req.typenames: CLFS_CONTEXT_MODE, *PCLFS_CONTEXT_MODE, PPCLFS_CONTEXT_MODE
---

# _CLFS_CONTEXT_MODE enumeration


## -description


The <b>CLFS_CONTEXT_MODE</b> enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541682">ClfsReadLogRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541690">ClfsReadNextLogRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541699">ClfsReadPreviousRestartArea</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541709">ClfsReadRestartArea</a>
 

 

