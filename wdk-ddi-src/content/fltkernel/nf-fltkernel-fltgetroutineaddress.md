---
UID: NF:fltkernel.FltGetRoutineAddress
title: FltGetRoutineAddress function
author: windows-driver-content
description: The FltGetRoutineAddress routine returns a pointer to a routine specified by the FltMgrRoutineName parameter.
old-location: ifsk\fltgetroutineaddress.htm
old-project: ifsk
ms.assetid: b2b74e79-5840-41a0-8af3-3d13e209aea7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetRoutineAddress, FltApiRef_e_to_o_81848969-38e3-4f2f-bdc3-45027ea28202.xml, ifsk.fltgetroutineaddress, FltGetRoutineAddress routine [Installable File System Drivers], fltkernel/FltGetRoutineAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetRoutineAddress
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetRoutineAddress function


## -description


The <b>FltGetRoutineAddress</b> routine returns a pointer to a routine specified by the <i>FltMgrRoutineName</i> parameter. 


## -syntax


````
PVOID FltGetRoutineAddress(
  _In_ PCSTR FltMgrRoutineName
);
````


## -parameters




### -param FltMgrRoutineName [in]

Name of the filter manager routine to resolve. 


## -returns


If the routine name can be resolved, <b>FltGetRoutineAddress</b> returns a pointer to the routine. Otherwise, it returns <b>NULL</b>. 



## -remarks


<b>FltGetRoutineAddress</b> searches the filter manager's export table for the requested routine name. 

To get the addresses of other routines that are exported by the kernel or hardware abstraction layer (HAL), use <a href="..\wdm\nf-wdm-mmgetsystemroutineaddress.md">MmGetSystemRoutineAddress</a>. 

Note that in Windows 2000 and Windows XP, before FltGetRoutineAddress is called at least one minifilter on the system must call FltRegisterFilter. The call to FltRegisterFilter is necessary to initialize global data structures.



## -see-also

<a href="..\wdm\nf-wdm-mmgetsystemroutineaddress.md">MmGetSystemRoutineAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetRoutineAddress routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

