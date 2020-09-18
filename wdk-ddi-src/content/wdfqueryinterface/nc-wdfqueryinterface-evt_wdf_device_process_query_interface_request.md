---
UID: NC:wdfqueryinterface.EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST
title: EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST (wdfqueryinterface.h)
description: A driver's EvtDeviceProcessQueryInterfaceRequest event callback function examines another driver's request for access to a driver-defined interface, before the framework passes the interface to the requesting driver.
old-location: wdf\evtdeviceprocessqueryinterfacerequest.htm
tech.root: wdf
ms.assetid: b56fef85-4058-4942-90c0-36646164cd3e
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST callback function"]
ms.keywords: DFDeviceObjectDriverDefIntRef_e38de652-334f-4b7a-b455-22c0eea8d8fd.xml, EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST, EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST callback, EvtDeviceProcessQueryInterfaceRequest, EvtDeviceProcessQueryInterfaceRequest callback function, kmdf.evtdeviceprocessqueryinterfacerequest, wdf.evtdeviceprocessqueryinterfacerequest, wdfqueryinterface/EvtDeviceProcessQueryInterfaceRequest
req.header: wdfqueryinterface.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST
 - wdfqueryinterface/EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfQueryInterface.h
api_name:
 - EvtDeviceProcessQueryInterfaceRequest
---

# EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceProcessQueryInterfaceRequest</i> event callback function examines another driver's request for access to a driver-defined interface, before the framework passes the interface to the requesting driver.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param InterfaceType 

[in]
A pointer to the GUID that identifies the driver-defined interface.

### -param ExposedInterface 

[in, out]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure that describes the driver-defined interface and was provided by the driver that is requesting access to the interface.

### -param ExposedInterfaceSpecificData 

[in, out]
A pointer to additional, optional, driver-defined, interface-specific information. Framework-based drivers specify this value by providing a non-<b>NULL</b> <i>InterfaceSpecificData</i> parameter value when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>.

## -returns

If the <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function receives a GUID that it supports, and if the function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. The framework continues passing the request down the stack to see if additional drivers also support the interface.

The <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function must return STATUS_NOT_SUPPORTED if it determines that, for a particular case, it will not service the interface. The framework continues passing the request down the stack to see if another driver supports the interface. For more information about this situation, see the following Remarks section.



If the callback function encounters an error, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. The framework fails the other driver's request for the interface and does not pass the request down the stack.

## -remarks

Framework-based drivers register an <i>EvtDeviceProcessQueryInterfaceRequest</i> event callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

If the driver-defined interface supports only one-way communication and sets the <b>ImportInterface</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure that describes the interface to <b>FALSE</b>, the <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function is optional. When another driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>, the framework copies the driver-defined interface values into the requesting driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure and then calls the callback function. For one-way communication, you need to provide a callback function only if you want the driver to examine, and possibly modify, the interface values before the framework returns them to the requesting driver.

Your driver must provide an <i>EvtDeviceProcessQueryInterfaceRequest</i> event callback function if the driver defines an interface that supports two-way communication (and sets the <b>ImportInterface</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure to <b>TRUE</b>). The callback function is required because, if <b>ImportInterface</b> is <b>TRUE</b> and another driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>, the framework does not copy the driver-defined interface into the requesting driver's interface structure. Instead, the callback function must update the requesting driver's interface structure.

The callback function can modify the interface. In particular, it can:

<ul>
<li>
Change any value in any member of the interface.

</li>
<li>
Allocate a dynamic instance-specific context by modifying the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure.

</li>
</ul>
The framework calls your driver's <i>EvtDeviceProcessQueryInterfaceRequest</i> callback functions only for GUIDs that the driver has registered by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>. Therefore, these callback functions do not use the STATUS_NOT_SUPPORTED return value to report unexpected GUIDs. Instead, a <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function should return STATUS_NOT_SUPPORTED when it determines that, for a particular case, it will not handle the interface. For example, based on data that the requesting driver provides, your driver might determine that a lower-level driver should service the interface request. The STATUS_NOT_SUPPORTED return value informs the framework that your driver is not servicing the interface request, but a lower-level driver might service it. 

For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

To define an <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function that is named <i>MyDeviceProcessQueryInterfaceRequest</i>, use the <b>EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST</b> type as shown in this code example:


```
EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST  MyDeviceProcessQueryInterfaceRequest;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
 MyDeviceProcessQueryInterfaceRequest (
    WDFDEVICE  Device,
    LPGUID  InterfaceType,
    PINTERFACE  ExposedInterface,
    PVOID  ExposedInterfaceSpecificData
    )
  {...}
```

The <b>EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST</b> function type is defined in the WdfQueryInterface.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>

