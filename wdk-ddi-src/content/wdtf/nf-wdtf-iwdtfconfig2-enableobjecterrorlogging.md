---
UID: NF:wdtf.IWDTFCONFIG2.EnableObjectErrorLogging
title: IWDTFCONFIG2::EnableObjectErrorLogging method
author: windows-driver-content
description: Enables object error logging for all objects.
old-location: dtf\iwdtfconfig2_enableobjecterrorlogging.htm
old-project: dtf
ms.assetid: 10e7abc9-addd-4f0e-b77b-af9e8e1fa061
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: EnableObjectErrorLogging method [Windows Device Testing Framework], IWDTFCONFIG2 interface, IWDTFCONFIG2::EnableObjectErrorLogging, EnableObjectErrorLogging method [Windows Device Testing Framework], Microsoft.WDTF.IWDTFCONFIG2.EnableObjectErrorLogging, Microsoft::WDTF::IWDTFCONFIG2::EnableObjectErrorLogging, IWDTFCONFIG2 interface [Windows Device Testing Framework], EnableObjectErrorLogging method, wdtf/IWDTFCONFIG2::EnableObjectErrorLogging, IWDTFCONFIG2, EnableObjectErrorLogging, dtf.iwdtfconfig2_enableobjecterrorlogging
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFCONFIG2.EnableObjectErrorLogging
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFCONFIG2::EnableObjectErrorLogging method


## -description


Enables object error logging for all objects.


## -syntax


````
HRESULT EnableObjectErrorLogging();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



If object logging is enabled, object error logging is enabled by default. Otherwise, error
logging defaults to disabled.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfconfig2.md">IWDTFCONFIG2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFCONFIG2::EnableObjectErrorLogging method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

