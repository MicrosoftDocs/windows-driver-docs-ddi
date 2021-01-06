---
UID: NF:wdfrequest.WdfRequestWdmGetIrp
title: WdfRequestWdmGetIrp function (wdfrequest.h)
description: The WdfRequestWdmGetIrp method returns the WDM IRP structure that is associated with a specified framework request object.
old-location: wdf\wdfrequestwdmgetirp.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfRequestWdmGetIrp function"]
ms.keywords: DFRequestObjectRef_2f8bba17-817e-4edb-98f2-bd56eb3e34ac.xml, WdfRequestWdmGetIrp, WdfRequestWdmGetIrp method, kmdf.wdfrequestwdmgetirp, wdf.wdfrequestwdmgetirp, wdfrequest/WdfRequestWdmGetIrp
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestWdmGetIrp
 - wdfrequest/WdfRequestWdmGetIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfRequestWdmGetIrp
---

# WdfRequestWdmGetIrp function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestWdmGetIrp</b> method returns the WDM <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that is associated with a specified framework request object.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

## -returns

<b>WdfRequestWdmGetIrp</b> returns a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The driver must not access a request's IRP structure after <a href="/windows-hardware/drivers/wdf/completing-i-o-requests">completing the I/O request</a>.

For more information about <b>WdfRequestWdmGetIrp</b>, see <a href="/windows-hardware/drivers/wdf/obtaining-information-about-an-i-o-request">Obtaining Information About an I/O Request</a>.


#### Examples

The following code example is part of an <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a> callback function that obtains the WDM IRP that is associated with an I/O request and then calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetnextirpstacklocation">IoGetNextIrpStackLocation</a> to obtain the next-lower driver's I/O stack location.

```cpp
VOID
MyEvtIoDeviceControl(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  OutputBufferLength,
    IN size_t  InputBufferLength,
    IN ULONG  IoControlCode
    )
{
    PIRP  irp = NULL;
    PIO_STACK_LOCATION  nextStack;
...
    irp = WdfRequestWdmGetIrp(Request);
    nextStack = IoGetNextIrpStackLocation(irp);
...
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetparameters">WdfRequestGetParameters</a>
