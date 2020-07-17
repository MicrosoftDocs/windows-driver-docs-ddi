---
UID: NF:wpprecorder.imp_WppRecorderConfigure
title: imp_WppRecorderConfigure function (wpprecorder.h)
description: The WppRecorderConfigure method enables or disables the default log to which WPP prints.
old-location: devtest\wpprecorderconfigure.htm
tech.root: devtest
ms.assetid: 995E4606-F987-46A7-8310-28E8E9C7682C
ms.date: 02/23/2018
keywords: ["imp_WppRecorderConfigure function"]
ms.keywords: WppRecorderConfigure, devtest.wpprecorderconfigure, imp_WppRecorderConfigure, imp_WppRecorderConfigure function [Driver Development Tools], wpprecorder/imp_WppRecorderConfigure
f1_keywords:
 - "wpprecorder/imp_WppRecorderConfigure"
 - "imp_WppRecorderConfigure"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wpprecorder.h
api_name:
- imp_WppRecorderConfigure
product:
- Windows
targetos: Windows
req.typenames: 
---

# imp_WppRecorderConfigure function


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderconfigure">WppRecorderConfigure</a> method enables or disables the default log to which WPP prints.


## -parameters




### -param WppCb

<p>Pointer to a caller-allocated RECORDER_CONFIGURE_PARAMS structure.</p>


### -param ConfigureParams

Pointer to a caller-allocated RECORDER_CONFIGURE_PARAMS structure.


## -returns



Returns STATUS_SUCCESS if completed successfully.




## -remarks



Before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderconfigure">WppRecorderConfigure</a>, allocate a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/ns-wpprecorder-_recorder_configure_params">RECORDER_CONFIGURE_PARAMS</a> structure and initialize by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-recorder_configure_params_init">RECORDER_CONFIGURE_PARAMS_INIT</a>. 

This method only configures the default log. By default that log is enabled. If you have a custom log, you must disable the default log by setting the <b>CreateDefaultLog</b> to FALSE.



