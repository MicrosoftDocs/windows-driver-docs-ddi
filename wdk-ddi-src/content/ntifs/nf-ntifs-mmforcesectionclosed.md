---
UID: NF:ntifs.MmForceSectionClosed
title: MmForceSectionClosed function (ntifs.h)
description: The MmForceSectionClosed routine deletes the data and image sections for a file that is no longer in use.
old-location: ifsk\mmforcesectionclosed.htm
tech.root: ifsk
ms.assetid: aa598c4b-e840-41cb-81a3-719a5b1ee48b
ms.date: 04/16/2018
ms.keywords: MmForceSectionClosed, MmForceSectionClosed routine [Installable File System Drivers], ifsk.mmforcesectionclosed, mmref_d2466446-15b8-4152-a7ff-3ebe1f05cd68.xml, ntifs/MmForceSectionClosed
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmForceSectionClosed
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmForceSectionClosed function


## -description


The <b>MmForceSectionClosed</b> routine deletes the data and image sections for a file that is no longer in use. 


## -parameters




### -param SectionObjectPointer [in]

A pointer to a structure that contains the file object's section object pointers.


### -param DelayClose [in]

A Boolean value that specifies whether the section is subsequently deleted if <b>MmForceSectionClosed</b> cannot delete the section synchronously (that is, prior to <b>MmForceSectionClosed</b> returning). 

<b>TRUE</b> indicates that if <b>MmForceSectionClosed</b> cannot delete the section synchronously, <b>MmForceSectionClosed</b> sets a flag. With this flag set, when the section's outstanding reference count reaches zero, the memory manager deletes the section automatically. 

<b>FALSE</b> indicates that if <b>MmForceSectionClosed</b> cannot delete the section synchronously, the section is not deleted.


## -returns



<b>MmForceSectionClosed</b> returns <b>TRUE</b> if the sections were successfully deleted or no sections were found, <b>FALSE</b> otherwise.

<div class="alert"><b>Note</b>  If there are one or more outstanding write probes on the file's data section, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549808">MmFlushImageSection</a> returns <b>FALSE</b>.</div>
<div> </div>



## -remarks



For more information about creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563682">Sections and Views</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549808">MmFlushImageSection</a>
 

 

