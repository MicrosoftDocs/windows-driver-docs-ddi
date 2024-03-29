---
UID: NC:wdfrequest.EVT_WDF_REQUEST_COMPLETION_ROUTINE
title: EVT_WDF_REQUEST_COMPLETION_ROUTINE (wdfrequest.h)
description: A driver's CompletionRoutine event callback function executes when another driver completes a specified I/O request.
old-location: wdf\completionroutine.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_REQUEST_COMPLETION_ROUTINE callback function"]
ms.keywords: CompletionRoutine, CompletionRoutine callback function, DFRequestObjectRef_5eed5273-6939-4a56-846a-ee80c92c005a.xml, EVT_WDF_REQUEST_COMPLETION_ROUTINE, EVT_WDF_REQUEST_COMPLETION_ROUTINE callback, kmdf.completionroutine, wdf.completionroutine, wdfrequest/CompletionRoutine
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_REQUEST_COMPLETION_ROUTINE
 - wdfrequest/EVT_WDF_REQUEST_COMPLETION_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfrequest.h
api_name:
 - EVT_WDF_REQUEST_COMPLETION_ROUTINE
---

# EVT_WDF_REQUEST_COMPLETION_ROUTINE callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>CompletionRoutine</i> event callback function executes when another driver completes a specified I/O request.

## -parameters

### -param Request [in]


A handle to a framework request object that represents the completed I/O request.

### -param Target [in]


A handle to an I/O target object that represents the I/O target that completed the request.

### -param Params [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a> structure that contains information about the completed request. See note below regarding validity of the completion parameters.

### -param Context [in]


Driver-supplied context information, which the driver specified in a previous call to <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>.

## -remarks

To register a <i>CompletionRoutine</i> callback function for an I/O request, a driver must call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>. For more information about this callback function, see <a href="/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.

The completion parameters structure is fully populated with valid information only if the driver formatted the request by calling one of the following:

* <b>WdfIoTargetFormat</b><i>Xxx</i> methods, for example <a href="/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforread">WdfIoTargetFormatRequestForRead</a>
* <b>WdfUsbTargetDeviceFormatRequestFor</b><i>Xxx</i> methods, for example [**WdfUsbTargetDeviceFormatRequestForString**](../wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforstring.md)
* <b>WdfUsbTargetPipeFormatRequestFor</b><i>Xxx</i> methods, for example [**WdfUsbTargetPipeFormatRequestForWrite**](../wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforwrite.md)

If the driver formatted the request using either [**WdfRequestFormatRequestUsingCurrentType**](./nf-wdfrequest-wdfrequestformatrequestusingcurrenttype.md) or [**WdfRequestWdmFormatUsingStackLocation**](./nf-wdfrequest-wdfrequestwdmformatusingstacklocation.md), only the **IoStatus** field in the completion parameters structure is valid.

A KMDF driver's <i>CompletionRoutine</i> can run at IRQL <= DISPATCH_LEVEL regardless of the  <b>ExecutionLevel</b> specified in the <a href="/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure for the I/O request object.  


#### Examples

The function type is declared in <i>Wdfrequest.h</i>, as follows.


```
typedef VOID
  (EVT_WDF_REQUEST_COMPLETION_ROUTINE)(
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    IN PWDF_REQUEST_COMPLETION_PARAMS  Params,
    IN WDFCONTEXT  Context
    );

```

To define a <i>CompletionRoutine</i> callback function that is named <b>MyCompletionRoutine</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:


```
EVT_WDF_REQUEST_COMPLETION_ROUTINE  MyCompletionRoutine;
```

Then, implement your callback function as follows:


```
VOID
 MyCompletionRoutine (
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    IN PWDF_REQUEST_COMPLETION_PARAMS  Params,
    IN WDFCONTEXT  Context
    )
  {...}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_completion_params">WDF_REQUEST_COMPLETION_PARAMS</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>

