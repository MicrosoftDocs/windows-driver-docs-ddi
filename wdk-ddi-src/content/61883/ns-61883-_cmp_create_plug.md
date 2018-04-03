---
UID: NS:61883._CMP_CREATE_PLUG
title: "_CMP_CREATE_PLUG"
author: windows-driver-content
description: This structure is used to create a plug.
old-location: ieee\cmp_create_plug.htm
old-project: IEEE
ms.assetid: 4FE3FE9E-9F00-431D-99F0-002B1368CE34
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_CREATE_PLUG, 61883/CMP_CREATE_PLUG, 61883/PCMP_CREATE_PLUG, CMP_CREATE_PLUG, CMP_CREATE_PLUG structure [Buses], IEEE.cmp_create_plug, PCMP_CREATE_PLUG, PCMP_CREATE_PLUG structure pointer [Buses], _CMP_CREATE_PLUG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
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
-	61883.h
api_name:
-	CMP_CREATE_PLUG
product:
- Windows
targetos: Windows
req.typenames: CMP_CREATE_PLUG, *PCMP_CREATE_PLUG
---

# _CMP_CREATE_PLUG structure


## -description


This structure is used to create a plug. The request creates an input or output plug control register (iPCR or oPCR) on the local host. A driver is responsible for deleting all of the plugs it has created before the system unloads the driver.


## -struct-fields




### -field PlugType

On input, the type of plug to create. Can be one of the following:





#### CMP_PlugOut

An output plug, which transmits data from the device to the bus.



#### CMP_PlugIn

An input plug, which receives data sent by the bus to the device.


### -field Pcr

On input, an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537010">AV_PCR</a> structure that contains values used by the protocol driver to initialize the plug. 


### -field pfnNotify

On input, a pointer to a caller-supplied function to be called by the protocol driver when the plug is created. 


### -field Context

On input, a pointer to an optional caller-supplied context for the function at <b>pfnNotify</b>. 


### -field PlugNum

On output, the plug number. 


### -field hPlug

On output, the handle of the created plug

<b>PlugNum</b>
    
    The plug number of the newly created plug. If the plug could not be created, <b>PlugNum</b> is zero (0). 
    
     <b>hPlug</b>
    
    A handle to the newly created plug. If the plug could not be created, <b>hPlug</b> is null.

.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

