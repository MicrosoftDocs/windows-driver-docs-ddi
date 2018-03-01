---
UID: NF:ntifs.MmForceSectionClosed
title: MmForceSectionClosed function
author: windows-driver-content
description: The MmForceSectionClosed routine deletes the data and image sections for a file that is no longer in use.
old-location: ifsk\mmforcesectionclosed.htm
old-project: ifsk
ms.assetid: aa598c4b-e840-41cb-81a3-719a5b1ee48b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MmForceSectionClosed, MmForceSectionClosed routine [Installable File System Drivers], ifsk.mmforcesectionclosed, mmref_d2466446-15b8-4152-a7ff-3ebe1f05cd68.xml, ntifs/MmForceSectionClosed
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# MmForceSectionClosed function


## -description


The <b>MmForceSectionClosed</b> routine deletes the data and image sections for a file that is no longer in use. 


## -syntax


````
BOOLEAN MmForceSectionClosed(
  _In_ PSECTION_OBJECT_POINTERS SectionObjectPointer,
  _In_ BOOLEAN                  DelayClose
);
````


## -parameters




### -param SectionObjectPointer [in]

A pointer to a structure that contains the file object's section object pointers.


### -param DelayClose [in]

A Boolean value that specifies whether the section is subsequently deleted if <b>MmForceSectionClosed</b> cannot delete the section synchronously (that is, prior to <b>MmForceSectionClosed</b> returning). 

<b>TRUE</b> indicates that if <b>MmForceSectionClosed</b> cannot delete the section synchronously, <b>MmForceSectionClosed</b> sets a flag. With this flag set, when the section's outstanding reference count reaches zero, the memory manager deletes the section automatically. 

<b>FALSE</b> indicates that if <b>MmForceSectionClosed</b> cannot delete the section synchronously, the section is not deleted.


## -returns



<b>MmForceSectionClosed</b> returns <b>TRUE</b> if the sections were successfully deleted or no sections were found, <b>FALSE</b> otherwise.

<div class="alert"><b>Note</b>  If there are one or more outstanding write probes on the file's data section, <a href="..\ntifs\nf-ntifs-mmflushimagesection.md">MmFlushImageSection</a> returns <b>FALSE</b>.</div>
<div> </div>



## -remarks



For more information about creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563682">Sections and Views</a>.




## -see-also

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>



<a href="..\ntifs\nf-ntifs-mmflushimagesection.md">MmFlushImageSection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MmForceSectionClosed routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

