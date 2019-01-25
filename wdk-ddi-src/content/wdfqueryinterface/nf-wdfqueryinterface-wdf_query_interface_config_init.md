---
UID: NF:wdfqueryinterface.WDF_QUERY_INTERFACE_CONFIG_INIT
title: WDF_QUERY_INTERFACE_CONFIG_INIT function (wdfqueryinterface.h)
description: The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure.
old-location: wdf\wdf_query_interface_config_init.htm
tech.root: wdf
ms.assetid: 509f4fa5-37c8-4098-aade-767aad5d6d6a
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectDriverDefIntRef_d7e26200-d711-4c81-92d6-d2c2c1f052b0.xml, WDF_QUERY_INTERFACE_CONFIG_INIT, WDF_QUERY_INTERFACE_CONFIG_INIT function, kmdf.wdf_query_interface_config_init, wdf.wdf_query_interface_config_init, wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG_INIT
ms.topic: function
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfqueryinterface.h
api_name:
-	WDF_QUERY_INTERFACE_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_QUERY_INTERFACE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552439">WDF_QUERY_INTERFACE_CONFIG</a> structure.


## -parameters




### -param InterfaceConfig [out]

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552439">WDF_QUERY_INTERFACE_CONFIG</a> structure.


### -param Interface [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_interface">INTERFACE</a> structure.


### -param InterfaceType [in]

A pointer to the GUID that identifies the interface.


### -param EvtDeviceProcessQueryInterfaceRequest [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.


## -returns



None




## -remarks



For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545870">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552439">WDF_QUERY_INTERFACE_CONFIG</a>
 

 

