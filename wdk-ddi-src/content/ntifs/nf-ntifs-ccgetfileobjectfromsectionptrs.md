---
UID: NF:ntifs.CcGetFileObjectFromSectionPtrs
title: CcGetFileObjectFromSectionPtrs function
author: windows-driver-content
description: Given a pointer to the section object pointers for a cached file, the CcGetFileObjectFromSectionPtrs routine returns a pointer to the file object that the cache manager is using for the file.
old-location: ifsk\ccgetfileobjectfromsectionptrs.htm
old-project: ifsk
ms.assetid: da756f88-e2c6-4bff-8390-be48902fe130
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CcGetFileObjectFromSectionPtrs, CcGetFileObjectFromSectionPtrs routine [Installable File System Drivers], ccref_2e9f9f04-b5e3-47e5-beff-5e4d7181ca9d.xml, ifsk.ccgetfileobjectfromsectionptrs, ntifs/CcGetFileObjectFromSectionPtrs
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcGetFileObjectFromSectionPtrs
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcGetFileObjectFromSectionPtrs function


## -description


Given a pointer to the section object pointers for a cached file, the <b>CcGetFileObjectFromSectionPtrs</b> routine returns a pointer to the file object that the cache manager is using for the file.


## -parameters




### -param SectionObjectPointer [in]

Pointer to a structure containing the file object's section object pointers.


## -returns



A pointer to the file object, or <b>NULL</b> if the file is not cached or is no longer cached.




## -remarks



The file system is responsible for ensuring that the file object remains valid while in use. It is impossible for the cache manager to guarantee this. 

By using <b>CcGetFileObjectFromSectionPtrs</b>, you lose some caching functionality. Instead, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539113">CcGetFileObjectFromSectionPtrsRef</a> routine, which provides the same functionality as <b>CcGetFileObjectFromSectionPtrs</b> as well as creating a reference for the object.

For more information about creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563682">Sections and Views</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539113">CcGetFileObjectFromSectionPtrsRef</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

