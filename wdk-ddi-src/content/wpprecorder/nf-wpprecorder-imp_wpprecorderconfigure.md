---
UID: NF:wpprecorder.imp_WppRecorderConfigure
title: imp_WppRecorderConfigure function
author: windows-driver-content
description: The WppRecorderConfigure method enables or disables the default log to which WPP prints.
old-location: devtest\wpprecorderconfigure.htm
old-project: devtest
ms.assetid: 995E4606-F987-46A7-8310-28E8E9C7682C
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: WppRecorderConfigure, devtest.wpprecorderconfigure, imp_WppRecorderConfigure, imp_WppRecorderConfigure function [Driver Development Tools], wpprecorder/imp_WppRecorderConfigure
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
-	imp_WppRecorderConfigure
product:
- Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderConfigure function


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/dn914611">WppRecorderConfigure</a> method enables or disables the default log to which WPP prints.


## -parameters




### -param WppCb

TBD


### -param ConfigureParams

Pointer to a caller-allocated RECORDER_CONFIGURE_PARAMS structure.


## -returns



Returns STATUS_SUCCESS if completed successfully.




## -remarks



Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn914611">WppRecorderConfigure</a>, allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/dn914606">RECORDER_CONFIGURE_PARAMS</a> structure and initialize by calling <a href="https://msdn.microsoft.com/library/windows/hardware/dn914607">RECORDER_CONFIGURE_PARAMS_INIT</a>. 

This method only configures the default log. By default that log is enabled. If you have a custom log, you must disable the default log by setting the <b>CreateDefaultLog</b> to FALSE.



