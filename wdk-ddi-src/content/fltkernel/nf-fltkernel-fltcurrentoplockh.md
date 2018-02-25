---
UID: NF:fltkernel.FltCurrentOplockH
title: FltCurrentOplockH function
author: windows-driver-content
description: A minifilter driver calls the FltCurrentOplockH routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentoplockh.htm
old-project: ifsk
ms.assetid: ee066013-99fb-4a43-82f9-edbad7b5a8e9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FltApiRef_a_to_d_0abdd89d-fe36-4546-a3bd-87d7d132f73e.xml, FltCurrentOplockH, FltCurrentOplockH routine [Installable File System Drivers], H, O, c, e, fltkernel/FltCurrentOplockH, ifsk.fltcurrentoplockh, k, l, n, o, p, r, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCurrentOplockH routine is available starting with Windows 7.
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
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltCurrentOplockH
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCurrentOplockH function


## -description


A minifilter driver calls the <b>FltCurrentOplockH</b> routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. 


## -syntax


````
BOOLEAN FltCurrentOplockH(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentOplockH</b> returns <b>TRUE</b> if there are CACHE_HANDLE_LEVEL oplocks that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FltCurrentOplockH</b> returns <b>FALSE</b> if no CACHE_HANDLE_LEVEL opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentoplockh.md">FsRtlCurrentOplockH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCurrentOplockH routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

