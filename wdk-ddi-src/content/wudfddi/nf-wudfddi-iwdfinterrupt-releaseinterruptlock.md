---
UID: NF:wudfddi.IWDFInterrupt.ReleaseInterruptLock
title: IWDFInterrupt::ReleaseInterruptLock (wudfddi.h)
description: The ReleaseInterruptLock method ends a code sequence that executes while holding an interrupt object's lock.
old-location: wdf\iwdfinterrupt_releaseinterruptlock.htm
tech.root: wdf
ms.assetid: 55ED21D9-D704-4E38-AFCF-B1D1FDB67DB3
ms.date: 02/26/2018
ms.keywords: IWDFInterrupt interface,ReleaseInterruptLock method, IWDFInterrupt.ReleaseInterruptLock, IWDFInterrupt::ReleaseInterruptLock, ReleaseInterruptLock, ReleaseInterruptLock method, ReleaseInterruptLock method,IWDFInterrupt interface, umdf.iwdfinterrupt_releaseinterruptlock, wdf.iwdfinterrupt_releaseinterruptlock, wudfddi/IWDFInterrupt::ReleaseInterruptLock
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFInterrupt.ReleaseInterruptLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFInterrupt::ReleaseInterruptLock


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReleaseInterruptLock</b> method ends a code sequence that executes while holding an interrupt object's lock.


## -parameters






## -returns



This method does not return a value.




## -remarks



For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451283">IWDFInterrupt</a>



<a href="https://msdn.microsoft.com/2ED55AEC-2446-4E66-AAFD-A22BAB3FC9C7">IWDFInterrupt::AcquireInterruptLock</a>
 

 

