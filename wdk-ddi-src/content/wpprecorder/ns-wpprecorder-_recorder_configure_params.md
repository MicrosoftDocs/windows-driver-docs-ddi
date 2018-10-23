---
UID: NS:wpprecorder._RECORDER_CONFIGURE_PARAMS
title: "_RECORDER_CONFIGURE_PARAMS"
author: windows-driver-content
description: The RECORDER_CONFIGURE_PARAMS structure is an input parameter to the WppRecorderConfigure method to enable or disable the default log to which WPP prints.
old-location: devtest\recorder_configure_params.htm
tech.root: devtest
ms.assetid: 9D2AB7D0-CD75-4539-9CB8-8CBA33EFE299
ms.date: 02/23/2018
ms.keywords: "*PRECORDER_CONFIGURE_PARAMS, PRECORDER_CONFIGURE_PARAMS, PRECORDER_CONFIGURE_PARAMS structure pointer [Driver Development Tools], RECORDER_CONFIGURE_PARAMS, RECORDER_CONFIGURE_PARAMS structure [Driver Development Tools], _RECORDER_CONFIGURE_PARAMS, devtest.recorder_configure_params, wpprecorder/PRECORDER_CONFIGURE_PARAMS, wpprecorder/RECORDER_CONFIGURE_PARAMS"
ms.topic: struct
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wpprecorder.h
api_name:
-	RECORDER_CONFIGURE_PARAMS
product:
- Windows
targetos: Windows
req.typenames: RECORDER_CONFIGURE_PARAMS, *PRECORDER_CONFIGURE_PARAMS
---

# _RECORDER_CONFIGURE_PARAMS structure


## -description


The <b>RECORDER_CONFIGURE_PARAMS</b> structure is an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn914611">WppRecorderConfigure</a> method to enable or disable the default log to which WPP prints.


## -struct-fields




### -field Size

Size of this structure.


### -field CreateDefaultLog

Indicates whether WPP should use the default log for trace messages. TRUE (default), use the default log; FALSE disable the default log.


## -remarks



To initialize this structure, the caller must call <a href="https://msdn.microsoft.com/library/windows/hardware/dn914607">RECORDER_CONFIGURE_PARAMS_INIT</a>.



