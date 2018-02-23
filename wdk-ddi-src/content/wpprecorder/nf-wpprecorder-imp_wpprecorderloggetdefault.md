---
UID: NF:wpprecorder.imp_WppRecorderLogGetDefault
title: imp_WppRecorderLogGetDefault function
author: windows-driver-content
description: The WppRecorderLogGetDefault method gets a handle to the default recorder log.
old-location: devtest\wpprecorderloggetdefault.htm
old-project: devtest
ms.assetid: 823E9AA6-F838-41B1-A502-A983B7F24661
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WppRecorderLogGetDefault, imp_WppRecorderLogGetDefault function [Driver Development Tools], imp_WppRecorderLogGetDefault, devtest.wpprecorderloggetdefault, wpprecorder/imp_WppRecorderLogGetDefault
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wpprecorder.h
apiname:
-	imp_WppRecorderLogGetDefault
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# imp_WppRecorderLogGetDefault function


## -description


The <b>WppRecorderLogGetDefault</b> method gets a handle to the default recorder log.


## -syntax


````
RECORDER_LOG imp_WppRecorderLogGetDefault(void);
````


## -parameters




### -param WppCb

TBD




## -returns



An opaque handle to the default log.




## -see-also

<a href="..\wpprecorder\nf-wpprecorder-imp_wpprecorderisdefaultlogavailable.md">WppRecorderIsDefaultLogAvailable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20imp_WppRecorderLogGetDefault function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

