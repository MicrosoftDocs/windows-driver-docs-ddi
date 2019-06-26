---
UID: NF:fltkernel.FltCurrentOplockH
title: FltCurrentOplockH function (fltkernel.h)
description: A minifilter driver calls the FltCurrentOplockH routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.
old-location: ifsk\fltcurrentoplockh.htm
tech.root: ifsk
ms.assetid: ee066013-99fb-4a43-82f9-edbad7b5a8e9
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_0abdd89d-fe36-4546-a3bd-87d7d132f73e.xml, FltCurrentOplockH, FltCurrentOplockH routine [Installable File System Drivers], fltkernel/FltCurrentOplockH, ifsk.fltcurrentoplockh
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCurrentOplockH
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCurrentOplockH function


## -description


A minifilter driver calls the <b>FltCurrentOplockH</b> routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>. 


## -returns



<b>FltCurrentOplockH</b> returns <b>TRUE</b> if there are CACHE_HANDLE_LEVEL oplocks that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FltCurrentOplockH</b> returns <b>FALSE</b> if no CACHE_HANDLE_LEVEL opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltinitializeoplock">FltInitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentoplockh">FsRtlCurrentOplockH</a>
 

 

