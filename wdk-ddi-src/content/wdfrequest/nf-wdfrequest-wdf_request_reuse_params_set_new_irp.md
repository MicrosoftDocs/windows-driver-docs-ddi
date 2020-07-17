---
UID: NF:wdfrequest.WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
title: WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function (wdfrequest.h)
description: The WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function sets a new IRP in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_params_set_new_irp.htm
tech.root: wdf
ms.assetid: 3a18ec1b-be02-418a-8a38-deca7178ce30
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function"]
ms.keywords: DFRequestObjectRef_1c9cbd6c-35a3-4de2-84f9-9d9788002d31.xml, WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP, WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function, kmdf.wdf_request_reuse_params_set_new_irp, wdf.wdf_request_reuse_params_set_new_irp, wdfrequest/WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
f1_keywords:
 - "wdfrequest/WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP"
 - "WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP"
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
- WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets a new IRP in a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -parameters




### -param Params [in, out]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.


### -param NewIrp [in]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure.


## -remarks



If a driver's call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a> specifies a new IRP structure, the driver must first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_reuse_params_init">WDF_REQUEST_REUSE_PARAMS_INIT</a> and then call <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> to initialize a WDF_REQUEST_REUSE_PARAMS structure.

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets the structure's <b>NewIrp</b> member to the specified IRP pointer. It also sets the <b>WDF_REQUEST_REUSE_SET_NEW_IRP</b> flag in the structure's <b>Flag</b> member.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure, provides a new IRP structure for the I/O request, and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>.

```cpp
WDF_REQUEST_REUSE_PARAMS  params;
NTSTATUS  status;
PIRP  myIrp;
...
WDF_REQUEST_REUSE_PARAMS_INIT(
                              &params,
                              WDF_REQUEST_REUSE_NO_FLAGS,
                              STATUS_SUCCESS
                              );
WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP(
                                     &params,
                                     myIrp
                                     );
status = WdfRequestReuse(
                         Request,
                         &params
                         );
...
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_reuse_params_init">WDF_REQUEST_REUSE_PARAMS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>
 

 

