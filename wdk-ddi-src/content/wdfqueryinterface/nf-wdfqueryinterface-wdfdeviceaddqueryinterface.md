---
UID: NF:wdfqueryinterface.WdfDeviceAddQueryInterface
title: WdfDeviceAddQueryInterface function (wdfqueryinterface.h)
description: The WdfDeviceAddQueryInterface method creates a driver-defined interface that other drivers can query and use.
old-location: wdf\wdfdeviceaddqueryinterface.htm
tech.root: wdf
ms.assetid: 6e811b5e-bd2a-473b-8e5c-52bfbd9b8f7c
ms.date: 02/26/2018
keywords: ["WdfDeviceAddQueryInterface function"]
ms.keywords: DFDeviceObjectDriverDefIntRef_6d1dbdca-5adf-4641-91c9-7c59e2af6869.xml, WdfDeviceAddQueryInterface, WdfDeviceAddQueryInterface method, kmdf.wdfdeviceaddqueryinterface, wdf.wdfdeviceaddqueryinterface, wdfqueryinterface/WdfDeviceAddQueryInterface
req.header: wdfqueryinterface.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceAddQueryInterface
 - wdfqueryinterface/WdfDeviceAddQueryInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceAddQueryInterface
---

# WdfDeviceAddQueryInterface function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceAddQueryInterface</b> method creates a driver-defined interface that other drivers can query and use.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param InterfaceConfig 

[in]
A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure that describes the interface.

## -returns

<b>WdfDeviceAddQueryInterface</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter (possibly including members of the WDF_QUERY_INTERFACE_CONFIG structure) was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the WDF_QUERY_INTERFACE_CONFIG structure was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
</table>
 

For a list of additional return values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.



This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.

## -remarks

Drivers that create driver-defined interfaces typically call <b>WdfDeviceAddQueryInterface</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function.

After a driver calls <b>WdfDeviceAddQueryInterface</b> to create a driver-defined interface, another framework-based driver can access the interface by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>.

For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

The following code example is from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample bus driver. This example creates a driver-defined interface that uses the toaster sample's TOASTER_INTERFACE_STANDARD structure.

```cpp
typedef struct _TOASTER_INTERFACE_STANDARD {
 INTERFACE  InterfaceHeader;
  PTOASTER_GET_CRISPINESS_LEVEL  GetCrispinessLevel;
  PTOASTER_SET_CRISPINESS_LEVEL  SetCrispinessLevel;
  PTOASTER_IS_CHILD_PROTECTED  IsSafetyLockEnabled;
} TOASTER_INTERFACE_STANDARD, *PTOASTER_INTERFACE_STANDARD;

TOASTER_INTERFACE_STANDARD  ToasterInterface;
WDF_QUERY_INTERFACE_CONFIG  qiConfig;

//
// Initialize the ToasterInterface structure.
//
RtlZeroMemory(
              &ToasterInterface,
              sizeof(ToasterInterface)
              );

ToasterInterface.InterfaceHeader.Size = sizeof(ToasterInterface);
ToasterInterface.InterfaceHeader.Version = 1;
ToasterInterface.InterfaceHeader.Context = (PVOID)hChild;

ToasterInterface.InterfaceHeader.InterfaceReference =
        WdfDeviceInterfaceReferenceNoOp;
ToasterInterface.InterfaceHeader.InterfaceDereference =
        WdfDeviceInterfaceDereferenceNoOp;

ToasterInterface.GetCrispinessLevel = Bus_GetCrispinessLevel;
ToasterInterface.SetCrispinessLevel = Bus_SetCrispinessLevel;
ToasterInterface.IsSafetyLockEnabled = Bus_IsSafetyLockEnabled;

//
// Initialize the qiConfig structure.
//
WDF_QUERY_INTERFACE_CONFIG_INIT(
                                &qiConfig,
                                (PINTERFACE)&ToasterInterface,
                                &GUID_TOASTER_INTERFACE_STANDARD,
                                NULL
                                );

//
// Create the interface.
//
status = WdfDeviceAddQueryInterface(
                                    hChild,
                                    &qiConfig
                                    );
if (!NT_SUCCESS(status)) {
    return status;
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdf_query_interface_config_init">WDF_QUERY_INTERFACE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop">WdfDeviceInterfaceDereferenceNoOp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop">WdfDeviceInterfaceReferenceNoOp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>

