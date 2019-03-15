---
UID: NF:ntddsd.SdBusOpenInterface
title: SdBusOpenInterface function (ntddsd.h)
description: The SdBusOpenInterface routine obtains an interface from the Secure Digital (SD) bus driver.
old-location: sd\sdbusopeninterface.htm
tech.root: SD
ms.assetid: a788cd28-81a7-4b8c-b9c5-76dd2b1cd0f3
ms.date: 02/15/2018
ms.keywords: SD.sdbusopeninterface, SdBusOpenInterface, SdBusOpenInterface function [Buses], ntddsd/SdBusOpenInterface, sd-rtns_44707c61-dadc-4151-b06a-8df3def56ab9.xml
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddsd.h
api_name:
- SdBusOpenInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdBusOpenInterface function


## -description


The <b>SdBusOpenInterface</b> routine obtains an interface from the Secure Digital (SD) bus driver.


## -parameters




### -param Pdo [in]

Pointer to the physical device object that the SD bus driver created for the SD device that the device driver manages. The system passes this pointer to the device driver when it calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param InterfaceStandard [out]

Contains, on input, a pointer to a structure of type <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> supplied by the caller. On output, this structure holds pointers to the SD bus interface routines. This structure also contains some context information in its <b>Context</b> member that the caller should pass in every time it calls an interface routine.


### -param Size [in]

Contains the size, in bytes, of the structure pointed to by <i>InterfaceStandard</i>.


### -param Version [in]

Must be set to SDBUS_INTERFACE_VERSION.


## -returns



Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error code if the operation fails. 




## -remarks



An SD card driver should call this routine from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.

SD card drivers must call this routine to establish communication with the bus driver. On successful completion of this call, the <b>Context</b> member of the structure pointed to by <i>InterfaceStandard</i> will contain a handle that the driver must pass in when calling methods that belong to the retrieved interface. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a>



<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>
 

 

