---
UID: NS:wdfqueryinterface._WDF_QUERY_INTERFACE_CONFIG
title: _WDF_QUERY_INTERFACE_CONFIG (wdfqueryinterface.h)
description: The WDF_QUERY_INTERFACE_CONFIG structure describes a driver-defined interface.
old-location: wdf\wdf_query_interface_config.htm
tech.root: wdf
ms.assetid: 2f7112fc-7f3e-415d-9994-ffd93f456d97
ms.date: 02/26/2018
keywords: ["WDF_QUERY_INTERFACE_CONFIG structure"]
ms.keywords: "*PWDF_QUERY_INTERFACE_CONFIG, DFDeviceObjectDriverDefIntRef_5b68f6e3-95f7-4339-91c2-2ea2d88d698b.xml, PWDF_QUERY_INTERFACE_CONFIG, PWDF_QUERY_INTERFACE_CONFIG structure pointer, WDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG structure, _WDF_QUERY_INTERFACE_CONFIG, kmdf.wdf_query_interface_config, wdf.wdf_query_interface_config, wdfqueryinterface/PWDF_QUERY_INTERFACE_CONFIG, wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG"
req.header: wdfqueryinterface.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WDF_QUERY_INTERFACE_CONFIG, *PWDF_QUERY_INTERFACE_CONFIG
f1_keywords:
 - _WDF_QUERY_INTERFACE_CONFIG
 - wdfqueryinterface/_WDF_QUERY_INTERFACE_CONFIG
 - PWDF_QUERY_INTERFACE_CONFIG
 - wdfqueryinterface/PWDF_QUERY_INTERFACE_CONFIG
 - WDF_QUERY_INTERFACE_CONFIG
 - wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfqueryinterface.h
api_name:
 - WDF_QUERY_INTERFACE_CONFIG
---

# _WDF_QUERY_INTERFACE_CONFIG structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_QUERY_INTERFACE_CONFIG</b> structure describes a driver-defined interface.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Interface

A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure that describes the driver-defined interface.

### -field InterfaceType

A pointer to the GUID that identifies the interface.

### -field SendQueryToParentStack

If <b>TRUE</b>, and if your driver specifies a device object that represents a physical device object (PDO) when it calls <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>, the framework sends requests for the interface to the top of the parent device's driver stack. If this member is <b>FALSE</b>, or if the device object does not represent a PDO, the framework does not send requests to the parent device's stack. For more information, see the following Remarks section.

### -field EvtDeviceProcessQueryInterfaceRequest

A pointer to your driver's <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.

### -field ImportInterface

If <b>TRUE</b>, the interface supports two-way communication between your driver and drivers that request the interface. 

If this member is <b>FALSE</b>, the interface supports one-way communication from your driver to drivers that request the interface.

## -remarks

The <b>WDF_QUERY_INTERFACE_CONFIG</b> structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a> method. 

For each driver-defined interface that your driver exports, you must allocate a WDF_QUERY_INTERFACE_CONFIG structure that represents the interface. Other drivers can request access to the interface by calling <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>. 

If you want your interface to support two-way communication between the requesting driver and your driver, set the <b>ImportInterface</b> member to <b>TRUE</b>. If <b>ImportInterface</b> is <b>TRUE</b>, the structure that is provided by the requesting driver can contain data that your driver can read. In this case:

<ul>
<li>
The <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a> callback function is required, and it must initialize the interface structure that the requesting driver provides. 

</li>
<li>
Because the <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a> callback function provides the interface to the requesting driver, the <b>Interface</b> member of <b>WDF_QUERY_INTERFACE_CONFIG</b> can be <b>NULL</b>. If you provide a non-<b>NULL</b> pointer, the framework verifies that the size and version values that the requesting driver supplies are equal to or less than the values in your <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. If either of these values are greater, the framework rejects the request. If you do not provide a value for <b>Interface</b>, your <i>EvtDeviceProcessQueryInterfaceRequest</i> callback function must verify those values.

</li>
</ul>
If you want your interface to support only one-way communication from your driver to the requesting driver, set <b>ImportInterface</b> is <b>FALSE</b>. The interface structure that the requesting driver provides can receive only data that your driver provides. In this case:

<ul>
<li>
The <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a> callback function is optional.

</li>
<li>
The <b>Interface</b> member cannot be <b>NULL</b>. The framework verifies that the GUID, size, and version values that the requesting driver supplies match the ones you supplied, and the framework rejects the request if the values do not match. If the values are valid, the framework initializes the interface structure that the requesting driver provides by using values the you supply for <b>Interface</b>.

</li>
</ul>
Additionally, the <b>Interface</b> member can be <b>NULL</b> if the value of the <b>SendQueryToParentStack</b> member is <b>TRUE</b>. 

If the <b>Interface</b> member is non-<b>NULL</b>, the framework copies the value to internal storage space. Therefore, the driver can allocate the INTERFACE structure in local, temporary storage space.

When your driver calls <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>, it can associate the interface with a framework device object that represents either a functional device object (FDO) or a physical device object (PDO). If the driver associates the interface with a PDO, it can set the <b>SendQueryToParentStack</b> member of the <b>WDF_QUERY_INTERFACE_CONFIG</b> structure to <b>TRUE</b>. When the framework intercepts a request for the interface, it checks the <b>SendQueryToParentStack</b> member and, if it is set to <b>TRUE</b>, the framework sends the request to the top of the driver stack of the PDO's parent. As a result, the request travels down two driver stacks: first, the stack that contains the driver that is requesting the interface and, second, the stack of the parent of the interface's device.

The framework provides two reference/dereference methods that you can use with your interfaces by specifying their addresses for the <b>InterfaceReference</b> and <b>InterfaceDereference</b> members of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure. For more information about these methods, see <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop">WdfDeviceInterfaceReferenceNoOp</a> and <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop">WdfDeviceInterfaceDereferenceNoOp</a>.

Drivers should initialize this structure by calling <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdf_query_interface_config_init">WDF_QUERY_INTERFACE_CONFIG_INIT</a>.

For more information about driver-defined interfaces, see <a href="/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nc-wdfqueryinterface-evt_wdf_device_process_query_interface_request">EvtDeviceProcessQueryInterfaceRequest</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdf_query_interface_config_init">WDF_QUERY_INTERFACE_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop">WdfDeviceInterfaceDereferenceNoOp</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop">WdfDeviceInterfaceReferenceNoOp</a>



<a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoqueryforinterface">WdfFdoQueryForInterface</a>