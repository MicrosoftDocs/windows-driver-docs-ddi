---
UID: NF:wdfrequest.WDF_REQUEST_REUSE_PARAMS_INIT
title: WDF_REQUEST_REUSE_PARAMS_INIT function (wdfrequest.h)
description: The WDF_REQUEST_REUSE_PARAMS_INIT function initializes a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_params_init.htm
tech.root: wdf
ms.assetid: a77d77c5-5c8a-439a-93a3-fe29b15c6ed0
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_REUSE_PARAMS_INIT function"]
ms.keywords: DFRequestObjectRef_e43a091a-a926-4705-8241-0620b6ef3096.xml, WDF_REQUEST_REUSE_PARAMS_INIT, WDF_REQUEST_REUSE_PARAMS_INIT function, kmdf.wdf_request_reuse_params_init, wdf.wdf_request_reuse_params_init, wdfrequest/WDF_REQUEST_REUSE_PARAMS_INIT
f1_keywords:
 - "wdfrequest/WDF_REQUEST_REUSE_PARAMS_INIT"
 - "WDF_REQUEST_REUSE_PARAMS_INIT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfrequest.h
api_name:
- WDF_REQUEST_REUSE_PARAMS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_REUSE_PARAMS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -parameters




### -param Params [out]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.


### -param Flags [in]


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_reuse_flags">WDF_REQUEST_REUSE_FLAGS</a>-typed flags. 


### -param Status [in]

An NTSTATUS value that the framework assigns to the request.


## -remarks



Before a driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a> method, it must call <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.

The <b>WDF_REQUEST_REUSE_PARAMS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure and sets the structures <b>Size</b> member. It also sets the structure's <b>Flags</b> and <b>Status</b> members to the specified values.

For a code example that uses <b>WDF_REQUEST_REUSE_PARAMS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_reuse_params_set_new_irp">WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>
 

 

