---
UID: NF:wdfqueryinterface.WdfDeviceInterfaceDereferenceNoOp
title: WdfDeviceInterfaceDereferenceNoOp function (wdfqueryinterface.h)
description: The WdfDeviceInterfaceDereferenceNoOp method can be used for driver-defined interfaces that do not require reference counts.
old-location: wdf\wdfdeviceinterfacedereferencenoop.htm
tech.root: wdf
ms.assetid: 76319a0b-a7b3-48f6-804b-e01bc360c441
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectDriverDefIntRef_2bfa96a8-a58a-4408-83db-11670d7de8c7.xml, WdfDeviceInterfaceDereferenceNoOp, WdfDeviceInterfaceDereferenceNoOp method, kmdf.wdfdeviceinterfacedereferencenoop, wdf.wdfdeviceinterfacedereferencenoop, wdfqueryinterface/WdfDeviceInterfaceDereferenceNoOp
ms.topic: function
f1_keywords:
 - "wdfqueryinterface/WdfDeviceInterfaceDereferenceNoOp"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInterfaceDereferenceNoOp
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInterfaceDereferenceNoOp function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInterfaceDereferenceNoOp</b> method can be used for driver-defined interfaces that do not require reference counts.


## -parameters




### -param Context [in]

This parameter is not used.


## -returns



None




## -remarks



You can use the <b>WdfDeviceInterfaceDereferenceNoOp</b> method's address as the <b>InterfaceDereference</b> member of the <a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-netbt-interfaces-interface">INTERFACE</a> structure that is contained in the framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a> structure.

For more information about interface reference counts and the <b>WdfDeviceInterfaceDereferenceNoOp</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WdfDeviceInterfaceDereferenceNoOp</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceaddqueryinterface">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-netbt-interfaces-interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfqueryinterface/ns-wdfqueryinterface-_wdf_query_interface_config">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfqueryinterface/nf-wdfqueryinterface-wdfdeviceinterfacereferencenoop">WdfDeviceInterfaceReferenceNoOp</a>
 

 

