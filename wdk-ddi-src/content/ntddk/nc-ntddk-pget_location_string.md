---
UID: NC:ntddk.PGET_LOCATION_STRING
title: PGET_LOCATION_STRING (ntddk.h)
description: The PnpGetLocationString routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.
old-location: kernel\pnpgetlocationstring.htm
tech.root: kernel
ms.assetid: 03ebdeed-10f0-4633-a9cd-4db683a8c3a7
ms.date: 04/30/2018
keywords: ["PGET_LOCATION_STRING callback function"]
ms.keywords: PGET_LOCATION_STRING, PnpGetLocationString, PnpGetLocationString routine [Kernel-Mode Driver Architecture], drvr_interface_86bd2a9c-408f-430f-9ab7-5c368600de1e.xml, kernel.pnpgetlocationstring, ntddk/PnpGetLocationString
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PGET_LOCATION_STRING
 - ntddk/PGET_LOCATION_STRING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PnpGetLocationString
---

# PGET_LOCATION_STRING callback function


## -description

The <i>PnpGetLocationString</i> routine provides the device-specific part of the device's SPDRP_LOCATION_PATHS property.

## -parameters

### -param Context 

[in, out]
A pointer to interface-specific context information.  The caller passes the value that is passed as the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pnp_location_interface">PNP_LOCATION_INTERFACE</a> structure.

### -param LocationStrings 

[out]
A pointer to a sequence of null-terminated Unicode strings, that is terminated by another zero. Each string serves as a location string for the device. Drivers typically return a single string.

## -returns

The routine returns an NTSTATUS value to indicate the status of the operation.

## -remarks

The <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pnp_location_interface">PNP_LOCATION_INTERFACE</a> structure supplies a pointer to the <i>PnpGetLocationString</i> routine.

The <i>PnpGetLocationString</i> routine provides the device-specific part of the location string for the device.  The Plug and Play (PnP) manager assembles the location string for a device by querying the driver for the device, for the device's bus, and any parent buses, and concatenating the provided strings together.

The routine must return a string that is unique to the device relative to its bus. The string must be the same for the device across all versions of the operating system. Once you select a string for this purpose, you must not change it.

By convention, the location string takes the form <i>ServiceName(BusSpecificLocation)</i>. For example, PCI devices use PCI(<i>XXYY</i>), where <i>XX</i> is the device number, and <i>YY</i> is the function number.

The <i>PnpGetLocationString</i> routine calls a routine such as <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> to allocate the memory for the location string. The caller is responsible for calling the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> routine to free the memory pointed to by <i>LocationStrings</i> when the location string is no longer needed.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pnp_location_interface">PNP_LOCATION_INTERFACE</a>