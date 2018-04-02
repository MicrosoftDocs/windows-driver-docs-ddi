---
UID: NF:wdfresource.WdfIoResourceRequirementsListSetInterfaceType
title: WdfIoResourceRequirementsListSetInterfaceType function
author: windows-driver-content
description: The WdfIoResourceRequirementsListSetInterfaceType method assigns a bus type to a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistsetinterfacetype.htm
old-project: wdf
ms.assetid: c229eb9e-cf1f-43ea-b701-fb8fb6196b40
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_3ce545f1-cdad-4ddb-8b65-236461296d21.xml, WdfIoResourceRequirementsListSetInterfaceType, WdfIoResourceRequirementsListSetInterfaceType method, kmdf.wdfioresourcerequirementslistsetinterfacetype, wdf.wdfioresourcerequirementslistsetinterfacetype, wdfresource/WdfIoResourceRequirementsListSetInterfaceType
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoResourceRequirementsListSetInterfaceType
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceRequirementsListSetInterfaceType function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceRequirementsListSetInterfaceType</b> method assigns a bus type to a resource requirements list. 


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param InterfaceType [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff547839">INTERFACE_TYPE</a>-typed value that identifies the type of bus that the device is connected to. 


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Your driver must provide a bus type if your device does not support Plug and Play (PnP). 

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/bacd7e7c-9f71-4dda-98ed-a8d813360943">EvtDeviceResourceRequirementsQuery</a> callback function for a nonPnP device calls <b>WdfIoResourceRequirementsListSetInterfaceType</b> to assign a bus type to a device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceResourceRequirementsQuery(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST Requirements
    )
{
...
    WdfIoResourceRequirementsListSetInterfaceType(
                                                  Requirements,
                                                  Isa
                                                  );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547839">INTERFACE_TYPE</a>
 

 

