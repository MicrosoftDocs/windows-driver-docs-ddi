---
UID: NF:fltkernel.FltOplockKeysEqual
title: FltOplockKeysEqual function
author: windows-driver-content
description: The FltOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects.
old-location: ifsk\fltoplockkeysequal.htm
old-project: ifsk
ms.assetid: 660aa6f2-03d8-44aa-b263-29a74c912668
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltkernel/FltOplockKeysEqual, FltApiRef_e_to_o_66634abf-9f0a-44b1-a4e4-85ef958b05f5.xml, FltOplockKeysEqual, FltOplockKeysEqual routine [Installable File System Drivers], ifsk.fltoplockkeysequal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltOplockKeysEqual
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOplockKeysEqual function


## -description


The <b>FltOplockKeysEqual</b> routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. 


## -syntax


````
BOOLEAN FltOplockKeysEqual(
  _In_opt_ PFILE_OBJECT Fo1,
  _In_opt_ PFILE_OBJECT Fo2
);
````


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

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockkeysequal~r1.md">FsRtlOplockKeysEqual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockKeysEqual routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

