---
UID: NF:portcls.IPort.Init
title: IPort::Init (portcls.h)
description: The Init method initializes the port driver.
tech.root: audio
ms.assetid: 57c68de4-8063-41c0-897c-bc22c9a2b0f1
ms.date: 10/31/2018
keywords: ["IPort::Init"]
f1_keywords:
 - "portcls/IPort.Init"
ms.keywords: IPort::Init, Init, IPort.Init, IPort::Init, IPort.Init
req.header: portcls.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - COM
api_location: 
 - portcls.h
api_name: 
 - IPort.Init
product: 
 - Windows
targetos: Windows

---

# IPort::Init


## -description

The Init method initializes the port driver.

## -parameters

### -param DeviceObject
Pointer to the device object that was passed as an argument to the adapter driver's device-startup routine. The device object is a system structure of type DEVICE_OBJECT.

### -param Irp
Pointer to the IRP that was passed as an argument to the adapter driver's device-startup routine.

### -param UnknownMiniport
Pointer to the IUnknown interface of the uninitialized miniport object. This interface is queried for the specific miniport interface supported by the port driver, and the initialization function on that interface is called.


### -param UnknownAdapter
Pointer to the IUnknown interface of the adapter object whose port driver is being initialized. This pointer is optional and can be specified as NULL. For more information, see the following Remarks section.


### -param ResourceList
Pointer to the IResourceList object that was passed as an argument to the adapter driver's device-startup routine. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list.


## -returns
This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The miniport object specified by UnknownMiniport must support the miniport interface that the port driver requires or the Init call will fail.

During the IPort::Init call, the port driver calls the miniport driver's initialization method (for example, see IMiniportWavePci::Init).

Parameter UnknownAdapter points to the COM interface of an adapter object. The adapter driver typically creates this object within its device-startup routine, which is the routine that the operating system calls to start the device (see Startup Sequence). For an example of an interface for an adapter object, see the definition and implementation of the IAdapterObject interface in the sb16 and msvad sample audio drivers in the Microsoft Windows Driver Kit (WDK).

The UnknownMiniport, UnknownAdapter, and ResourceList parameters follow the reference-counting conventions for COM objects.


## -see-also

[IPort](nn-portcls-iport.md)
