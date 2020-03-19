---
UID: NS:usbcamdi.__unnamed_struct_0
title: USBCAMD_INTERFACE (usbcamdi.h)
description: The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces.
old-location: stream\usbcamd_interface.htm
tech.root: stream
ms.assetid: 864dbe8d-2771-4532-8a50-ed1bf5286658
ms.date: 04/23/2018
keywords: ["USBCAMD_INTERFACE structure"]
ms.keywords: "*PUSBCAMD_INTERFACE, PUSBCAMD_INTERFACE, PUSBCAMD_INTERFACE structure pointer [Streaming Media Devices], USBCAMD_INTERFACE, USBCAMD_INTERFACE structure [Streaming Media Devices], stream.usbcamd_interface, usbcamdi/PUSBCAMD_INTERFACE, usbcamdi/USBCAMD_INTERFACE, usbcmdpr_113d60d6-c353-468a-9c3d-801c76caf7be.xml"
f1_keywords:
 - "usbcamdi/USBCAMD_INTERFACE"
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
- usbcamdi.h
api_name:
- USBCAMD_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: USBCAMD_INTERFACE, *PUSBCAMD_INTERFACE
---

# USBCAMD_INTERFACE structure


## -description


The USBCAMD_INTERFACE structure defines a set of services related to the USB bus interfaces.


## -struct-fields




### -field Interface

Describes the interface that USBCAMD exports for use by other drivers.


### -field USBCAMD_WaitOnDeviceEvent

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_waitondeviceevent">USBCAMD_WaitOnDeviceEvent</a> service.


### -field USBCAMD_BulkReadWrite

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_bulkreadwrite">USBCAMD_BulkReadWrite</a> service.


### -field USBCAMD_SetVideoFormat

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_setvideoformat">USBCAMD_SetVideoFormat</a> service.


### -field USBCAMD_SetIsoPipeState

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_setisopipestate">USBCAMD_SetIsoPipeState</a> service.


### -field USBCAMD_CancelBulkReadWrite

Pointer to the camera minidriver defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_cancelbulkreadwrite">USBCAMD_CancelBulkReadWrite</a> service.


## -remarks



The camera minidriver may obtain the USBCAMD_INTERFACE entry points at any point after it has received <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-initialization-complete">SRB_INITIALIZATION_COMPLETE</a>. The IRP for acquiring a USBCAMD_INTERFACE is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> and must be sent at IRQL = PASSIVE_LEVEL. Typically, a camera minidriver obtains the addresses of the USBCAMD_INTERFACE entry points once toward the end of the initialization of the camera minidriver. The members of the USBCAMD_INTERFACE structure are filled with the minidriver's entry points as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/acquiring-usbcamd2-features">Acquiring USBCAMD2 Features</a>


<b>USBCAMD_INTERFACE</b> is not supported in the original USBCAMD.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-initialization-complete">SRB_INITIALIZATION_COMPLETE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_bulkreadwrite">USBCAMD_BulkReadWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_cancelbulkreadwrite">USBCAMD_CancelBulkReadWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_setisopipestate">USBCAMD_SetIsoPipeState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_setvideoformat">USBCAMD_SetVideoFormat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pfnusbcamd_waitondeviceevent">USBCAMD_WaitOnDeviceEvent</a>
 

 

