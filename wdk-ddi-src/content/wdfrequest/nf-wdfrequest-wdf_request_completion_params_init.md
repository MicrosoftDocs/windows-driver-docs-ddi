---
UID: NF:wdfrequest.WDF_REQUEST_COMPLETION_PARAMS_INIT
title: WDF_REQUEST_COMPLETION_PARAMS_INIT function
author: windows-driver-content
description: The WDF_REQUEST_COMPLETION_PARAMS_INIT function initializes a WDF_REQUEST_COMPLETION_PARAMS structure.
old-location: wdf\wdf_request_completion_params_init.htm
old-project: wdf
ms.assetid: f13e9474-7805-4c58-983d-4cfea4f005cc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_f92844e3-5003-45db-9684-608301b1ec32.xml, WDF_REQUEST_COMPLETION_PARAMS_INIT, WDF_REQUEST_COMPLETION_PARAMS_INIT function, kmdf.wdf_request_completion_params_init, wdf.wdf_request_completion_params_init, wdfrequest/WDF_REQUEST_COMPLETION_PARAMS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_COMPLETION_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_COMPLETION_PARAMS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -parameters




### -param Params [out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure.


## -returns



None




## -remarks



Drivers must call <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549961">WdfRequestGetCompletionParams</a>.

The <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Type</b> member to <b>WdfRequestTypeNoFormat</b>.


#### Examples

For a code example that uses <b>WDF_REQUEST_COMPLETION_PARAMS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549961">WdfRequestGetCompletionParams</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552454">WDF_REQUEST_COMPLETION_PARAMS</a>
 

 

