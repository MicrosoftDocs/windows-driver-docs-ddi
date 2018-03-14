---
UID: NF:wdfqueryinterface.WDF_QUERY_INTERFACE_CONFIG_INIT
title: WDF_QUERY_INTERFACE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_QUERY_INTERFACE_CONFIG_INIT function initializes a driver's WDF_QUERY_INTERFACE_CONFIG structure.
old-location: wdf\wdf_query_interface_config_init.htm
old-project: wdf
ms.assetid: 509f4fa5-37c8-4098-aade-767aad5d6d6a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectDriverDefIntRef_d7e26200-d711-4c81-92d6-d2c2c1f052b0.xml, WDF_QUERY_INTERFACE_CONFIG_INIT, WDF_QUERY_INTERFACE_CONFIG_INIT function, kmdf.wdf_query_interface_config_init, wdf.wdf_query_interface_config_init, wdfqueryinterface/WDF_QUERY_INTERFACE_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WDF_PDO_EVENT_CALLBACKS, *PWDF_PDO_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# WDF_QUERY_INTERFACE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.


## -syntax


````
VOID WDF_QUERY_INTERFACE_CONFIG_INIT(
  _Out_          PWDF_QUERY_INTERFACE_CONFIG                    InterfaceConfig,
  _In_           PINTERFACE                                     Interface,
  _In_     const GUID                                           *InterfaceType,
  _In_opt_       PFN_WDF_DEVICE_PROCESS_QUERY_INTERFACE_REQUEST EvtDeviceProcessQueryInterfaceRequest
);
````


## -parameters




### -param InterfaceConfig [out]

A pointer to the driver's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.


### -param Interface [in]

A pointer to an <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure.


### -param InterfaceType [in]

A pointer to the GUID that identifies the interface.


### -param EvtDeviceProcessQueryInterfaceRequest [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a> event callback function, which is called when another driver requests the interface.


## -returns



None




## -remarks



For more information about driver-defined interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.


#### Examples

For a code example that uses <b>WDF_QUERY_INTERFACE_CONFIG_INIT</b>, see <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



<a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a>



<a href="https://msdn.microsoft.com/b56fef85-4058-4942-90c0-36646164cd3e">EvtDeviceProcessQueryInterfaceRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_QUERY_INTERFACE_CONFIG_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

