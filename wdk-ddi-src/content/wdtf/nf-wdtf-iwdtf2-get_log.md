---
UID: NF:wdtf.IWDTF2.get_Log
title: IWDTF2::get_Log method
author: windows-driver-content
description: Gets the WDTF log object.
old-location: dtf\iwdtf2_log.htm
old-project: dtf
ms.assetid: 4c229367-bcdc-466f-ae38-f5c56ae4b840
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTF2, IWDTF2 interface [Windows Device Testing Framework], Log property, IWDTF2.Log, IWDTF2::get_Log, Log property [Windows Device Testing Framework], Log property [Windows Device Testing Framework], IWDTF2 interface, Microsoft.WDTF.IWDTF2.Log, Microsoft::WDTF::IWDTF2::Log, dtf.iwdtf2_log, get_Log,IWDTF2.get_Log, wdtf/IWDTF2::Log, wdtf/IWDTF2::get_Log
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTF2.Log
-	IWDTF2.get_Log
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTF2::get_Log method


## -description


Gets the WDTF log object.

This property is read-only.


## -syntax


````
HRESULT get_Log(
  [out, retval] IWDTFLog2 **ppLog
);
````


## -parameters


## -see-also

<a href="..\wdtf\nn-wdtf-iwdtf2.md">IWDTF2</a>



<a href="..\wdtf\nn-wdtf-iwdtflog2.md">IWDTFLog2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTF2::Log property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

