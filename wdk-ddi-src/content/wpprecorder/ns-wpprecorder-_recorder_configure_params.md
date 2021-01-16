---
UID: NS:wpprecorder._RECORDER_CONFIGURE_PARAMS
title: _RECORDER_CONFIGURE_PARAMS (wpprecorder.h)
description: The RECORDER_CONFIGURE_PARAMS structure is an input parameter to the WppRecorderConfigure method to enable or disable the default log to which WPP prints.
old-location: devtest\recorder_configure_params.htm
tech.root: devtest
ms.date: 02/23/2018
keywords: ["RECORDER_CONFIGURE_PARAMS structure"]
ms.keywords: "*PRECORDER_CONFIGURE_PARAMS, PRECORDER_CONFIGURE_PARAMS, PRECORDER_CONFIGURE_PARAMS structure pointer [Driver Development Tools], RECORDER_CONFIGURE_PARAMS, RECORDER_CONFIGURE_PARAMS structure [Driver Development Tools], _RECORDER_CONFIGURE_PARAMS, devtest.recorder_configure_params, wpprecorder/PRECORDER_CONFIGURE_PARAMS, wpprecorder/RECORDER_CONFIGURE_PARAMS"
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
targetos: Windows
req.typenames: RECORDER_CONFIGURE_PARAMS, *PRECORDER_CONFIGURE_PARAMS
f1_keywords:
 - _RECORDER_CONFIGURE_PARAMS
 - wpprecorder/_RECORDER_CONFIGURE_PARAMS
 - PRECORDER_CONFIGURE_PARAMS
 - wpprecorder/PRECORDER_CONFIGURE_PARAMS
 - RECORDER_CONFIGURE_PARAMS
 - wpprecorder/RECORDER_CONFIGURE_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - _RECORDER_CONFIGURE_PARAMS
 - PRECORDER_CONFIGURE_PARAMS
 - RECORDER_CONFIGURE_PARAMS
---

# _RECORDER_CONFIGURE_PARAMS structure


## -description

The <b>RECORDER_CONFIGURE_PARAMS</b> structure is an input parameter to the <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-wpprecorderconfigure">WppRecorderConfigure</a> method to enable or disable the default log to which WPP prints.

## -struct-fields

### -field Size

Size of this structure.

### -field CreateDefaultLog

Indicates whether WPP should use the default log for trace messages. TRUE (default), use the default log; FALSE disable the default log.

## -remarks

To initialize this structure, the caller must call <a href="/windows-hardware/drivers/ddi/wpprecorder/nf-wpprecorder-recorder_configure_params_init">RECORDER_CONFIGURE_PARAMS_INIT</a>.

