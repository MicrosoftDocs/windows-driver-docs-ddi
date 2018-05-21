---
UID: NF:winsplp.ImpersonatePrinterClient
title: ImpersonatePrinterClient function
author: windows-driver-content
description: ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by RevertToPrinterSelf.
old-location: print\impersonateprinterclient.htm
old-project: print
ms.assetid: 8e110b2a-9d13-4e2e-8f27-5a48d838fb3c
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: ImpersonatePrinterClient, ImpersonatePrinterClient function [Print Devices], print.impersonateprinterclient, spoolfnc_2eb48193-850d-43dc-8e9b-025c8187c49e.xml, winsplp/ImpersonatePrinterClient
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
-	ImpersonatePrinterClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# ImpersonatePrinterClient function


## -description


ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by <a href="https://msdn.microsoft.com/library/windows/hardware/ff561987">RevertToPrinterSelf</a>.


## -parameters




### -param hToken [in]

Caller-supplied handle to a thread. This parameter must have been previously returned by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561987">RevertToPrinterSelf</a>.


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>. The caller can obtain an error code by calling GetLastError (described in the Microsoft Windows SDK documentation).




## -remarks



This function must be called after a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561987">RevertToPrinterSelf</a>. It resumes impersonation of the client and cleans up the thread handle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561987">RevertToPrinterSelf</a>
 

 

