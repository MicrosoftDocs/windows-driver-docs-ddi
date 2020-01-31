---
UID: NF:wdfrequest.WdfRequestWdmFormatUsingStackLocation
title: WdfRequestWdmFormatUsingStackLocation function (wdfrequest.h)
description: The WdfRequestWdmFormatUsingStackLocation method formats an I/O request by copying the contents of a specified WDM I/O stack location structure to the next stack location in the request.
old-location: wdf\wdfrequestwdmformatusingstacklocation.htm
tech.root: wdf
ms.assetid: 9ee3d748-f9aa-43d6-b472-7b55d2034fc7
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_a210a31a-e3a5-4bbd-af19-5be5f7651757.xml, WdfRequestWdmFormatUsingStackLocation, WdfRequestWdmFormatUsingStackLocation method, kmdf.wdfrequestwdmformatusingstacklocation, wdf.wdfrequestwdmformatusingstacklocation, wdfrequest/WdfRequestWdmFormatUsingStackLocation
f1_keywords:
 - "wdfrequest/WdfRequestWdmFormatUsingStackLocation"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfRequestWdmFormatUsingStackLocation
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestWdmFormatUsingStackLocation function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestWdmFormatUsingStackLocation</b> method formats an I/O request by copying the contents of a specified WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> structure to the next stack location in the request.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param Stack [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure that contains driver-supplied information. 


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <b>WdfRequestWdmFormatUsingStackLocation</b> method copies the information that is supplied by the <i>Stack</i> parameter into the next IRP stack location in the request. 

<b>WdfRequestWdmFormatUsingStackLocation</b> formats the request independent of whether the I/O target object of the request is local or remote.

If you want to set a completion routine for the request, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a> after calling <b>WdfRequestWdmFormatUsingStackLocation</b>.

For more information about <b>WdfRequestWdmFormatUsingStackLocation</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example supplies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure for an I/O request, sets a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function, and then sends the request to an I/O target.

```cpp
IO_STACK_LOCATION  ioStackLocation;
BOOLEAN sendStatus;
...
//
// Initialize the IO_STACK_LOCATION structure here.
//
...
//
// Assign the IO_STACK_LOCATION structure to the request.
//
WdfRequestWdmFormatUsingStackLocation(
                                      request,
                                      &ioStackLocation
                                      );
//
// Assign a CompletionRoutine callback function.
//
WdfRequestSetCompletionRoutine(
                               Request,
                               RequestTimeoutComplete,
                               NULL
                               );
//
// Send the request.
//
sendStatus = WdfRequestSend(
                            Request,
                            target,
                            NULL
                            );
```

The following code example illustrates how to send a PnP [IRP_MN_QUERY_CAPABILITIES](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-capabilities) IRP to an IO target.

```cpp
target = WdfDeviceGetIoTarget(Device);
status = WdfRequestCreate(WDF_NO_OBJECT_ATTRIBUTES,
                          target,
                          &request);

if (!NT_SUCCESS(status)) {
    // Log failure and leave
}

//
// PnP IRPs must be initialized with STATUS_NOT_SUPPORTED
//
WDF_REQUEST_REUSE_PARAMS_INIT(&reuse,
                              WDF_REQUEST_REUSE_NO_FLAGS,
                              STATUS_NOT_SUPPORTED);

WdfRequestReuse(request, &reuse);


//
// Initialize device capabilities
//
RtlZeroMemory(Capabilities, sizeof(DEVICE_CAPABILITIES));
Capabilities->Size = sizeof(DEVICE_CAPABILITIES);
Capabilities->Version  =  1;
Capabilities->Address  = (ULONG) -1;
Capabilities->UINumber = (ULONG) -1;
RtlZeroMemory(&stack, sizeof(stack));
stack.MajorFunction = IRP_MJ_PNP;
stack.MinorFunction = IRP_MN_QUERY_CAPABILITIES;
stack.Parameters.DeviceCapabilities.Capabilities = Capabilities;

WdfRequestWdmFormatUsingStackLocation(request, &stack);

WDF_REQUEST_SEND_OPTIONS_INIT(&options,
                              WDF_REQUEST_SEND_OPTION_SYNCHRONOUS);

if (WdfRequestSend(request, target, &options) == FALSE) {
    // Log failure
}

status = WdfRequestGetStatus(request);

if (!NT_SUCCESS(status)) {
    // Log failure
}

// Remember to delete the WDFREQUEST after creating it
if (request != NULL) {
    WdfObjectDelete(request);
}
```

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>
 

 

