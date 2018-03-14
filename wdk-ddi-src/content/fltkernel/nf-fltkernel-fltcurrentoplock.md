---
UID: NF:fltkernel.FltCurrentOplock
title: FltCurrentOplock function
author: windows-driver-content
description: A minifilter driver calls the FltCurrentOplock routine to determine whether there are any opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentoplock.htm
old-project: ifsk
ms.assetid: e503b016-3271-4cce-a7fc-09c04b56716d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_cda1ee2b-1ce2-40a3-8e55-25846f59f611.xml, FltCurrentOplock, FltCurrentOplock routine [Installable File System Drivers], fltkernel/FltCurrentOplock, ifsk.fltcurrentoplock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCurrentOplock routine is available starting with Windows 7.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCurrentOplock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCurrentOplock function


## -description


A minifilter driver calls the <b>FltCurrentOplock</b> routine to determine whether there are any opportunistic locks (oplocks) on a file. 


## -syntax


````
BOOLEAN FltCurrentOplock(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentOplock</b> returns <b>TRUE</b> if there are oplocks that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FltCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentoplock.md">FsRtlCurrentOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



 

 


