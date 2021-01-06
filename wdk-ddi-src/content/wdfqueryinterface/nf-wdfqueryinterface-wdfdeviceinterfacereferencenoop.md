---
UID: NF:wdfqueryinterface.WdfDeviceInterfaceReferenceNoOp
title: WdfDeviceInterfaceReferenceNoOp function (wdfqueryinterface.h)
description: The WdfDeviceInterfaceReferenceNoOp method can be used for driver-defined interfaces that do not require reference counts.
old-location: wdf\wdfdeviceinterfacereferencenoop.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceInterfaceReferenceNoOp function"]
ms.keywords: DFDeviceObjectDriverDefIntRef_8acb0e5a-ff60-4779-ae97-c6a3c0214365.xml, WdfDeviceInterfaceReferenceNoOp, WdfDeviceInterfaceReferenceNoOp method, kmdf.wdfdeviceinterfacereferencenoop, wdf.wdfdeviceinterfacereferencenoop, wdfqueryinterface/WdfDeviceInterfaceReferenceNoOp
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
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInterfaceReferenceNoOp
 - wdfqueryinterface/WdfDeviceInterfaceReferenceNoOp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceInterfaceReferenceNoOp
---

# WdfDeviceInterfaceReferenceNoOp function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInterfaceReferenceNoOp</b> method can be used for driver-defined interfaces that do not require reference counts.

## -parameters

### -param Context 

[in]
This parameter is not used.

## -remarks

You can use the <b>WdfDeviceInterfaceReferenceNoOp</b> method's address as the <b>InterfaceReference</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure that is contained in the framework's <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.

For more information about interface reference counts and the <b>WdfDeviceInterfaceReferenceNoOp</b> method, see <a href="/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WdfDeviceInterfaceReferenceNoOp</b>, see <a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop">WdfDeviceInterfaceDereferenceNoOp</a>
