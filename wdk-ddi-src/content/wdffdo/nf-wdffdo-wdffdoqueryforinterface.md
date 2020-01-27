---
UID: NF:wdffdo.WdfFdoQueryForInterface
title: WdfFdoQueryForInterface function (wdffdo.h)
description: The WdfFdoQueryForInterface method obtains access to another driver's GUID-identified interface.
old-location: wdf\wdffdoqueryforinterface.htm
tech.root: wdf
ms.assetid: 12bbc77b-c1cd-4899-aff2-e18e0d58b6b9
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_949fcc50-3604-4970-9516-666da06e3c9e.xml, WdfFdoQueryForInterface, WdfFdoQueryForInterface method, kmdf.wdffdoqueryforinterface, wdf.wdffdoqueryforinterface, wdffdo/WdfFdoQueryForInterface
f1_keywords:
 - "wdffdo/WdfFdoQueryForInterface"
req.header: wdffdo.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFdoQueryForInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoQueryForInterface function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoQueryForInterface</b> method obtains access to another driver's GUID-identified interface.


## -parameters




### -param Fdo

<p>A handle to a framework device object.</p>


### -param InterfaceType [in]

A pointer to a GUID that identifies the interface.


### -param Interface [out]

A pointer to a driver-allocated structure that receives the requested interface. This structure is defined by the driver that exports the requested interface and must begin with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -param Size [in]

The size, in bytes, of the driver-allocated structure that represents the requested interface.


### -param Version [in]

The version number of the requested interface. The format of this value is defined by the driver that exports the requested interface.


### -param InterfaceSpecificData [in, optional]

Additional interface-specific information. This parameter is optional and can be <b>NULL</b>.


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The device object is invalid or if the <i>Device</i>, <i>InterfaceType</i>, or <i>Interface</i> parameter is <b>NULL</b>. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate a request to send to another driver. 

</td>
</tr>
</table>
 

The method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Your driver can call <b>WdfFdoQueryForInterface</b> to obtain access to a driver-defined interface that was created by a driver that is in the same driver stack that your driver is in. To access a driver-defined interface that was created by a driver that is in a different driver stack, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface">WdfIoTargetQueryForInterface</a>.

Framework-based drivers define interfaces by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>. 

For more information about <b>WdfFdoQueryForInterface</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample function driver. This example obtains access to an interface that the toaster sample bus driver defines.

```cpp
status = WdfFdoQueryForInterface(
                                 Device,
                                 &GUID_TOASTER_INTERFACE_STANDARD,
                                 (PINTERFACE) &fdoData->BusInterface, // Object context space
                                 sizeof(TOASTER_INTERFACE_STANDARD),
                                 1,
                                 NULL
                                 );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetqueryforinterface">WdfIoTargetQueryForInterface</a>
 

 

