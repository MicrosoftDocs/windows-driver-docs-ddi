---
UID: NC:ntddsd.PSDBUS_INITIALIZE_INTERFACE_ROUTINE
title: PSDBUS_INITIALIZE_INTERFACE_ROUTINE
author: windows-driver-content
description: The PSDBUS_INITIALIZE_INTERFACE_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver uses to initialize an interface instance that it creates with the SdBusOpenInterface routine.
old-location: sd\psdbus_initialize_interface_routine.htm
old-project: SD
ms.assetid: 90d36eb1-d122-4266-9c33-206c9c9b44e8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: InitializeInterface, InitializeInterface callback function [Buses], PSDBUS_INITIALIZE_INTERFACE_ROUTINE, PSDBUS_INITIALIZE_INTERFACE_ROUTINE callback, SD.psdbus_initialize_interface_routine, ntddsd/InitializeInterface, sd-rtns_7716bd48-1f82-4b8e-b688-016bb0716e57.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntddsd.h
api_name:
-	InitializeInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSDBUS_INITIALIZE_INTERFACE_ROUTINE callback function


## -description


The PSDBUS_INITIALIZE_INTERFACE_ROUTINE prototype declares the routine that a Secure Digital (SD) device driver uses to initialize an interface instance that it creates with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine.


## -parameters




### -param Context [in]

Contains the interface context that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine returns in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a> structure.


### -param InterfaceParameters [in]

Pointer to a structure of type <a href="https://msdn.microsoft.com/d407131e-5dda-4d50-b09a-0f937774eefb">SDBUS_INTERFACE_PARAMETERS</a> that contains the information that the bus driver should use to initialize the interface instance.


## -returns



Returns STATUS_SUCCESS if the operation succeeds, or the appropriate error status if the operation fails.




## -remarks



An SD card driver typically calls its initialization routine immediately after the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a> routine returns with a value of STATUS_SUCCESS. 

An SD card driver must call its initialization routine before attempting to send requests to the bus driver.




## -see-also




<a href="https://msdn.microsoft.com/92b8762d-8af3-493c-aa1d-bc245b0cbd83">SDBUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537906">SdBusOpenInterface</a>
 

 

