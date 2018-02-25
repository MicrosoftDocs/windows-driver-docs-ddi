---
UID: NF:wpprecorder.RECORDER_CONFIGURE_PARAMS_INIT
title: RECORDER_CONFIGURE_PARAMS_INIT function
author: windows-driver-content
description: The RECORDER_CONFIGURE_PARAMS_INIT function is used to initialize the RECORDER_CONFIGURE_PARAMS structure.
old-location: devtest\recorder_configure_params_init.htm
old-project: devtest
ms.assetid: 840716D6-505E-4654-A54D-ABAF3A553E5E
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , A, C, D, E, F, G, I, M, N, O, P, R, RECORDER_CONFIGURE_PARAMS_INIT, RECORDER_CONFIGURE_PARAMS_INIT function [Driver Development Tools], S, T, U, _, devtest.recorder_configure_params_init, wpprecorder/RECORDER_CONFIGURE_PARAMS_INIT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wpprecorder.h
req.include-header: 
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
-	RECORDER_CONFIGURE_PARAMS_INIT
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# RECORDER_CONFIGURE_PARAMS_INIT function


## -description


The <b>RECORDER_CONFIGURE_PARAMS_INIT</b> function is used to initialize the <a href="..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md">RECORDER_CONFIGURE_PARAMS</a> structure.


## -syntax


````
FORCEINLINE void RECORDER_CONFIGURE_PARAMS_INIT(
  _Out_ PRECORDER_CONFIGURE_PARAMS   Params
);
````


## -parameters




### -param Params [out]

A pointer to the <a href="..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md">RECORDER_CONFIGURE_PARAMS</a> structure to initialize.


## -returns



This function does not return a value.




## -see-also

<a href="..\wpprecorder\ns-wpprecorder-_recorder_configure_params.md">RECORDER_CONFIGURE_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20RECORDER_CONFIGURE_PARAMS_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

