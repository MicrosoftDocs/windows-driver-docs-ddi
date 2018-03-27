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


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentOplock</b> returns <b>TRUE</b> if there are oplocks that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FltCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545833">FsRtlCurrentOplock</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCurrentOplock routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

