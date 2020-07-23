---
UID: NF:fltkernel.FltOplockKeysEqual
title: FltOplockKeysEqual function (fltkernel.h)
description: The FltOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.
old-location: ifsk\fltoplockkeysequal.htm
tech.root: ifsk
ms.assetid: 660aa6f2-03d8-44aa-b263-29a74c912668
ms.date: 04/16/2018
keywords: ["FltOplockKeysEqual function"]
ms.keywords: FltApiRef_e_to_o_66634abf-9f0a-44b1-a4e4-85ef958b05f5.xml, FltOplockKeysEqual, FltOplockKeysEqual routine [Installable File System Drivers], fltkernel/FltOplockKeysEqual, ifsk.fltoplockkeysequal
f1_keywords:
 - "fltkernel/FltOplockKeysEqual"
 - "FltOplockKeysEqual"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltOplockKeysEqual routine is available starting with Windows 8.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltOplockKeysEqual
targetos: Windows
req.typenames: 
---

# FltOplockKeysEqual function


## -description


The <b>FltOplockKeysEqual</b> routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. 


## -parameters




### -param Fo1 [in, optional]

A pointer to the first file object for the comparison. 


### -param Fo2 [in, optional]

A pointer to the second file object for the comparison. 


## -returns



The <b>FltOplockKeysEqual</b> routine returns <b>TRUE</b> if the keys match or if the file object pointers are the same. <b>FltOplockKeysEqual</b> returns <b>FALSE</b> if the keys do not match, if either of the file objects is missing, or if either of the file objects does not have a key. 




## -remarks



If no oplock key was provided when the file objects were created, the file objects are considered to match if the file object pointers are the same (that is, they are the same file object). If the file object pointers are different and either or both of the file objects do not have an associated oplock key, the file objects are considered to not match.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockkeysequal">FsRtlOplockKeysEqual</a>
 

 

