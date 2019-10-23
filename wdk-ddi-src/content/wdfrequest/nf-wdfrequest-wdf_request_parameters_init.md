---
UID: NF:wdfrequest.WDF_REQUEST_PARAMETERS_INIT
title: WDF_REQUEST_PARAMETERS_INIT function (wdfrequest.h)
description: The WDF_REQUEST_PARAMETERS_INIT function initializes a WDF_REQUEST_PARAMETERS structure.
old-location: wdf\wdf_request_parameters_init.htm
tech.root: wdf
ms.assetid: c4e83638-4931-460f-848b-ceb0f7a00afb
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_1c1e97cb-9ca1-473a-aa30-d39fdadbc726.xml, WDF_REQUEST_PARAMETERS_INIT, WDF_REQUEST_PARAMETERS_INIT function, kmdf.wdf_request_parameters_init, wdf.wdf_request_parameters_init, wdfrequest/WDF_REQUEST_PARAMETERS_INIT
ms.topic: function
f1_keywords:
 - "wdfrequest/WDF_REQUEST_PARAMETERS_INIT"
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
- WDF_REQUEST_PARAMETERS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_PARAMETERS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure.


## -parameters




### -param Parameters [out]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure.


## -returns



None




## -remarks



Drivers must call <b>WDF_REQUEST_PARAMETERS_INIT</b> to initialize a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>.

The <b>WDF_REQUEST_PARAMETERS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>.

```cpp
VOID
MyEvtIoDefault(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request
    )
{
    WDF_REQUEST_PARAMETERS  params;

    WDF_REQUEST_PARAMETERS_INIT(&params);

    WdfRequestGetParameters(
                            Request,
                            &params
                            );
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_parameters">WDF_REQUEST_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
 

 

