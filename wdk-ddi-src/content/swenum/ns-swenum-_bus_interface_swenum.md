---
UID: NS:swenum._BUS_INTERFACE_SWENUM
title: "_BUS_INTERFACE_SWENUM"
author: windows-driver-content
description: The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface.
old-location: stream\bus_interface_swenum.htm
old-project: stream
ms.assetid: 7e667dd9-8ed1-49ef-a6ef-0d079d41db86
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: swenum/BUS_INTERFACE_SWENUM, PBUS_INTERFACE_SWENUM structure pointer [Streaming Media Devices], ks-struct_d2f7683d-30e1-4ff5-b494-57309987e181.xml, stream.bus_interface_swenum, swenum/PBUS_INTERFACE_SWENUM, BUS_INTERFACE_SWENUM, PBUS_INTERFACE_SWENUM, *PBUS_INTERFACE_SWENUM, BUS_INTERFACE_SWENUM structure [Streaming Media Devices], _BUS_INTERFACE_SWENUM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: swenum.h
req.include-header: Swenum.h
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
-	swenum.h
apiname:
-	BUS_INTERFACE_SWENUM
product: Windows
targetos: Windows
req.typenames: "*PBUS_INTERFACE_SWENUM, BUS_INTERFACE_SWENUM"
req.product: Windows 10 or later.
---

# _BUS_INTERFACE_SWENUM structure


## -description


The BUS_INTERFACE_SWENUM structure describes the demand-load bus enumerator object's interface.


## -syntax


````
typedef struct _BUS_INTERFACE_SWENUM {
  INTERFACE                  Interface;
  PFNREFERENCEDEVICEOBJECT   ReferenceDeviceObject;
  PFNDEREFERENCEDEVICEOBJECT DereferenceDeviceObject;
  PFNQUERYREFERENCESTRING    QueryReferenceString;
} BUS_INTERFACE_SWENUM, *PBUS_INTERFACE_SWENUM;
````


## -struct-fields




### -field Interface

Specifies the exported <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>.


### -field ReferenceDeviceObject

Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksreferencesoftwarebusobject.md">KsReferenceSoftwareBusObject</a> routine.


### -field DereferenceDeviceObject

Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksdereferencesoftwarebusobject.md">KsDereferenceSoftwareBusObject</a> routine.


### -field QueryReferenceString

Pointer to a driver-supplied <a href="..\swenum\nf-swenum-ksquerysoftwarebusinterface.md">KsQuerySoftwareBusInterface</a> routine.


## -remarks


A driver obtains a BUS_INTERFACE_SWENUM interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:
<ul>
<li>
Allocate and zero-fill a BUS_INTERFACE_SWENUM structure from the paged memory pool.

</li>
<li>
Create an IRP for the query interface request and get the next stack location for the new IRP.

</li>
<li>
In the new stack location, provide a pointer to the new BUS_INTERFACE_SWENUM structure in the <b>Parameters.QueryInterface.Interface</b> member.

</li>
<li>
Set a completion routine and send the request down the driver stack.

</li>
<li>
If your request is successful, the system fills in the BUS_INTERFACE_SWENUM structure pointed to by <b>Parameters.QueryInterface.Interface</b>.

</li>
</ul>

