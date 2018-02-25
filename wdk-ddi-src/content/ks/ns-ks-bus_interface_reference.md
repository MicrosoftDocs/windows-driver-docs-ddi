---
UID: NS:ks.BUS_INTERFACE_REFERENCE
title: BUS_INTERFACE_REFERENCE
author: windows-driver-content
description: A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.
old-location: stream\bus_interface_reference.htm
old-project: stream
ms.assetid: 17c2c46c-ff79-4c80-82c9-c49b18426789
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PBUS_INTERFACE_REFERENCE, ,, A, B, BUS_INTERFACE_REFERENCE, BUS_INTERFACE_REFERENCE structure [Streaming Media Devices], C, E, F, I, N, P, PBUS_INTERFACE_REFERENCE, PBUS_INTERFACE_REFERENCE structure pointer [Streaming Media Devices], R, S, T, U, _, ks-struct_815b7147-1ae1-48d2-bae3-3efce2613b53.xml, ks/BUS_INTERFACE_REFERENCE, ks/PBUS_INTERFACE_REFERENCE, stream.bus_interface_reference"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	BUS_INTERFACE_REFERENCE
product: Windows
targetos: Windows
req.typenames: BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE
---

# BUS_INTERFACE_REFERENCE structure


## -description


A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.


## -syntax


````
typedef struct {
  INTERFACE                  Interface;
  PFNREFERENCEDEVICEOBJECT   ReferenceDeviceObject;
  PFNDEREFERENCEDEVICEOBJECT DereferenceDeviceObject;
  PFNQUERYREFERENCESTRING    QueryReferenceString;
} BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE;
````


## -struct-fields




### -field Interface

Specifies the exported <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.


### -field ReferenceDeviceObject

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567198">KStrReferenceDeviceObject</a> routine.


### -field DereferenceDeviceObject

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567170">KStrDereferenceDeviceObject</a> routine.


### -field QueryReferenceString

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff567193">KStrQueryReferenceString</a> routine.


## -remarks



A driver obtains a BUS_INTERFACE_REFERENCE interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:

<ul>
<li>
Allocate and zero-fill a BUS_INTERFACE_REFERENCE structure from the paged memory pool.

</li>
<li>
Create an IRP for the query interface request and get the next stack location for the new IRP.

</li>
<li>
In the new stack location, provide a pointer to the new BUS_INTERFACE_REFERENCE structure in the <b>Parameters.QueryInterface.Interface</b> member.

</li>
<li>
Set a completion routine and send the request down the driver stack.

</li>
<li>
If your request is successful, the system fills in the BUS_INTERFACE_REFERENCE structure pointed to by <b>Parameters.QueryInterface.Interface</b>.

</li>
</ul>


