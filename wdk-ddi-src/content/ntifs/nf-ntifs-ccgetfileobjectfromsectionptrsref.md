---
UID: NF:ntifs.CcGetFileObjectFromSectionPtrsRef
title: CcGetFileObjectFromSectionPtrsRef function
author: windows-driver-content
description: When passed a pointer to a SECTION_OBJECT_POINTERS structure for a cached file, the CcGetFileObjectFromSectionPtrsRef routine returns a pointer to the file object that the cache manager is using for the cached file.
old-location: ifsk\ccgetfileobjectfromsectionptrsref.htm
old-project: ifsk
ms.assetid: 8afbd8df-95fc-453f-a1d8-400a993c286a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ccref_e38ddec7-5501-40b4-a2a3-0a13c1c0fb4d.xml, CcGetFileObjectFromSectionPtrsRef, ntifs/CcGetFileObjectFromSectionPtrsRef, ifsk.ccgetfileobjectfromsectionptrsref, CcGetFileObjectFromSectionPtrsRef routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcGetFileObjectFromSectionPtrsRef
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcGetFileObjectFromSectionPtrsRef function


## -description


When passed a pointer to a SECTION_OBJECT_POINTERS structure for a cached file, the <b>CcGetFileObjectFromSectionPtrsRef</b> routine returns a pointer to the file object that the cache manager is using for the cached file.


## -syntax


````
PFILE_OBJECT CcGetFileObjectFromSectionPtrsRef(
  _In_ PSECTION_OBJECT_POINTERS SectionObjectPointer
);
````


## -parameters




### -param SectionObjectPointer [in]

A pointer to the <a href="..\wdm\ns-wdm-_section_object_pointers.md">SECTION_OBJECT_POINTERS</a> structure that is associated with the cached file.


## -returns



A pointer to the file object for the cached file, or <b>NULL</b> if the file is not cached or is no longer cached.




## -remarks



The file object is returned with a reference.  The caller is responsible for calling <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> on the file object when it has finished using the file object.




## -see-also

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\ntifs\nf-ntifs-ccgetfileobjectfromsectionptrs.md">CcGetFileObjectFromSectionPtrs</a>



<a href="..\wdm\ns-wdm-_section_object_pointers.md">SECTION_OBJECT_POINTERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetFileObjectFromSectionPtrsRef routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

