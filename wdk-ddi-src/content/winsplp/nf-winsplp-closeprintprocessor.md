---
UID: NF:winsplp.ClosePrintProcessor
title: ClosePrintProcessor function
author: windows-driver-content
description: A print processor's ClosePrintProcessor function completes the printing of a print job and makes the associated handle invalid.
old-location: print\closeprintprocessor.htm
old-project: print
ms.assetid: 3cf87a18-8b5a-40f2-9c0e-2b29167e283d
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: spoolfnc_f2e791a0-bfae-463c-a7ac-0e9f941ebe51.xml, ClosePrintProcessor function [Print Devices], print.closeprintprocessor, winsplp/ClosePrintProcessor, ClosePrintProcessor
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
req.lib: Nwprint.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Nwprint.lib
-	Nwprint.dll
apiname:
-	ClosePrintProcessor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ClosePrintProcessor function


## -description


A print processor's <b>ClosePrintProcessor</b> function completes the printing of a print job and makes the associated handle invalid.


## -syntax


````
BOOL ClosePrintProcessor(
  _Inout_ HANDLE hPrintProcessor
);
````


## -parameters




### -param hPrintProcessor [in, out]

Caller-supplied print processor handle. This is the handle returned by a previous call to <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. If the operation fails, the function should call SetLastError to set an error code, and then return <b>FALSE</b>.




## -remarks



Print processors are required to export a <b>ClosePrintProcessor</b> function. The spooler calls the function after the print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> returns. The function should free all resources that were allocated by the <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a> function.




## -see-also

<a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a>



<a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20ClosePrintProcessor function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

