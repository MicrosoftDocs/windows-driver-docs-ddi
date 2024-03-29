---
UID: NF:ntddsd.SdBusOpenInterface
title: SdBusOpenInterface function (ntddsd.h)
description: The SdBusOpenInterface routine obtains an interface from the Secure Digital (SD) bus driver.
old-location: sd\sdbusopeninterface.htm
tech.root: SD
ms.date: 02/15/2018
keywords: ["SdBusOpenInterface function"]
ms.keywords: SD.sdbusopeninterface, SdBusOpenInterface, SdBusOpenInterface function [Buses], ntddsd/SdBusOpenInterface, sd-rtns_44707c61-dadc-4151-b06a-8df3def56ab9.xml
req.header: ntddsd.h
req.include-header: Ntddsd.h
req.target-type: Desktop
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SdBusOpenInterface
 - ntddsd/SdBusOpenInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddsd.h
api_name:
 - SdBusOpenInterface
---

# SdBusOpenInterface function


## -description

The <b>SdBusOpenInterface</b> routine obtains an interface from the Secure Digital (SD) bus driver.

## -parameters

### -param Pdo [in]


Pointer to the physical device object that the SD bus driver created for the SD device that the device driver manages. The system passes this pointer to the device driver when it calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

### -param InterfaceStandard [out]


Contains, on input, a pointer to a structure of type <a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a> supplied by the caller. On output, this structure holds pointers to the SD bus interface routines. This structure also contains some context information in its <b>Context</b> member that the caller should pass in every time it calls an interface routine.

### -param Size [in]


Contains the size, in bytes, of the structure pointed to by <i>InterfaceStandard</i>.

### -param Version [in]


Must be set to SDBUS_INTERFACE_VERSION.

## -returns

Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails.

## -remarks

An SD card driver should call this routine from its <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

SD card drivers must call this routine to establish communication with the bus driver. On successful completion of this call, the <b>Context</b> member of the structure pointed to by <i>InterfaceStandard</i> will contain a handle that the driver must pass in when calling methods that belong to the retrieved interface.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>



<a href="/previous-versions/windows/hardware/drivers/ff537923(v=vs.85)">SDBUS_INTERFACE_STANDARD</a>
