---
UID: NS:ufxbase._UFX_HARDWARE_FAILURE_CONTEXT
title: _UFX_HARDWARE_FAILURE_CONTEXT (ufxbase.h)
description: The UFX_HARDWARE_FAILURE_CONTEXT structure is used to define controller-specific hardware failure properties.
old-location: buses\ufx_hardware_failure_context.htm
tech.root: usbref
ms.assetid: CA0268F3-44F0-4F64-A88D-9A2BBDE768EA
ms.date: 05/07/2018
ms.keywords: "*PUFX_HARDWARE_FAILURE_CONTEXT, PUFX_HARDWARE_FAILURE_CONTEXT, PUFX_HARDWARE_FAILURE_CONTEXT structure pointer [Buses], UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT structure [Buses], _UFX_HARDWARE_FAILURE_CONTEXT, buses.ufx_hardware_failure_context, ufxbase/PUFX_HARDWARE_FAILURE_CONTEXT, ufxbase/UFX_HARDWARE_FAILURE_CONTEXT"
ms.topic: struct
req.header: ufxbase.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ufxbase.h
api_name:
-	UFX_HARDWARE_FAILURE_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
---

# _UFX_HARDWARE_FAILURE_CONTEXT structure


## -description


The <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure is used to define controller-specific hardware failure properties. 


## -struct-fields




### -field Size

The size of the <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure.


### -field ExceptionCode

The controller-specific hardware failure code.


### -field Data

A variable-length array of data associated with the hardware failure.


## -remarks



In cases where the function controller has experienced a fatal error, the client driver may allocate a variable-length <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure, set the <b>Size</b> field to the allocated size, set the <b>ExceptionCode</b> field to a value indicating the type of hardware error (as defined by the client driver) and fill in any associated information in the <b>Data</b> array.  It may then pass this structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187957">UfxDeviceNotifyHardwareFailure</a> UFX function. UFX will in turn pass this structure to the client driver’s <a href="https://msdn.microsoft.com/library/windows/hardware/mt187848">EVT_UFX_DEVICE_CONTROLLER_RESET</a> event callback function (if it exists).



