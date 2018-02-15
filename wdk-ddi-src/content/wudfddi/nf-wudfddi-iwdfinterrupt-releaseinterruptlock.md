---
UID: NF:wudfddi.IWDFInterrupt.ReleaseInterruptLock
title: IWDFInterrupt::ReleaseInterruptLock method
author: windows-driver-content
description: The ReleaseInterruptLock method ends a code sequence that executes while holding an interrupt object's lock.
old-location: wdf\iwdfinterrupt_releaseinterruptlock.htm
old-project: wdf
ms.assetid: 55ED21D9-D704-4E38-AFCF-B1D1FDB67DB3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfinterrupt_releaseinterruptlock, ReleaseInterruptLock method, IWDFInterrupt interface, wdf.iwdfinterrupt_releaseinterruptlock, IWDFInterrupt interface, ReleaseInterruptLock method, wudfddi/IWDFInterrupt::ReleaseInterruptLock, ReleaseInterruptLock method, IWDFInterrupt::ReleaseInterruptLock, IWDFInterrupt, ReleaseInterruptLock
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFInterrupt.ReleaseInterruptLock
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFInterrupt::ReleaseInterruptLock method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReleaseInterruptLock</b> method ends a code sequence that executes while holding an interrupt object's lock.


## -syntax


````
void ReleaseInterruptLock();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



For more information about handling interrupts in UMDF drivers, see <a href="https://msdn.microsoft.com/25D526CF-7C37-4D10-B099-352933F92F98">Accessing Hardware and Handling Interrupts</a>.




## -see-also

<a href="https://msdn.microsoft.com/2ED55AEC-2446-4E66-AAFD-A22BAB3FC9C7">IWDFInterrupt::AcquireInterruptLock</a>



<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::ReleaseInterruptLock method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

