---
UID: NF:wdfresource.WdfIoResourceRequirementsListSetSlotNumber
title: WdfIoResourceRequirementsListSetSlotNumber function
author: windows-driver-content
description: The WdfIoResourceRequirementsListSetSlotNumber method assigns a slot number to a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistsetslotnumber.htm
old-project: wdf
ms.assetid: 1dc18c48-2331-4980-b741-59a73d3edaa6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFIORESOURCEREQUIREMENTSLISTSETSLOTNUMBER, kmdf.wdfioresourcerequirementslistsetslotnumber, WdfIoResourceRequirementsListSetSlotNumber, wdfresource/WdfIoResourceRequirementsListSetSlotNumber, DFResourceObjectRef_a4c6729c-ba18-49e0-8e8c-94c70c5c9e8a.xml, wdf.wdfioresourcerequirementslistsetslotnumber, WdfIoResourceRequirementsListSetSlotNumber method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoResourceRequirementsListSetSlotNumber
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceRequirementsListSetSlotNumber function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListSetSlotNumber</b> method assigns a slot number to a resource requirements list.


## -syntax


````
VOID WdfIoResourceRequirementsListSetSlotNumber(
  _In_ WDFIORESREQLIST RequirementsList,
  _In_ ULONG           SlotNumber
);
````


## -parameters




#### - RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


#### - SlotNumber [in]

A value that identifies the bus slot number to which the device is connected.


## -returns


None.

A system bug check occurs if the driver supplies an invalid object handle.



## -remarks


Your driver must provide a slot number if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


