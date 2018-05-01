---
UID: NF:winsplp.RevertToPrinterSelf
title: RevertToPrinterSelf function
author: windows-driver-content
description: When RevertToPrinterSelf is called on an impersonating thread, it returns the token for the thread that is being impersonated.
old-location: print\reverttoprinterself.htm
old-project: print
ms.assetid: 3d94d363-fc8b-4b12-b90d-43dfc5923bdf
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: RevertToPrinterSelf, RevertToPrinterSelf function [Print Devices], print.reverttoprinterself, spoolfnc_4cf3c4c1-39bf-4ef6-b578-b9ff0955cbe5.xml, winsplp/RevertToPrinterSelf
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	RevertToPrinterSelf
product: Windows
targetos: Windows
req.typenames: 
---

# RevertToPrinterSelf function


## -description


When <code>RevertToPrinterSelf</code> is called on an impersonating thread, it returns the token for the thread that is being impersonated.


## -parameters






#### - void


## -returns



If the operation succeeds, the function returns the token of the impersonated thread. If the current thread is not impersonating another thread, this function returns <b>NULL</b>.




## -remarks



<code>RevertToPrinterSelf</code> should be called when a component needs access to resources from the local system context, such as the registry. The local system context is the security context (the collection of settings that define the security behavior of a process or thread) of the system process. The system process is the process that runs in the logon session that is created for the local system account when the operating system boots. 

If <code>RevertToPrinterSelf</code> returns a non-<b>NULL</b> value, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551062">ImpersonatePrinterClient</a> must be called with the return value to complete the operation and clean up the thread handle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551062">ImpersonatePrinterClient</a>
 

 

