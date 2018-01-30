---
UID: NF:wdfqueryinterface.WdfDeviceInterfaceReferenceNoOp
title: WdfDeviceInterfaceReferenceNoOp function
author: windows-driver-content
description: The WdfDeviceInterfaceReferenceNoOp method can be used for driver-defined interfaces that do not require reference counts.
old-location: wdf\wdfdeviceinterfacereferencenoop.htm
old-project: wdf
ms.assetid: 9bb18fd3-e803-4f51-822e-88c06d3385cc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceInterfaceReferenceNoOp method, DFDeviceObjectDriverDefIntRef_8acb0e5a-ff60-4779-ae97-c6a3c0214365.xml, PFN_WDFDEVICEINTERFACEREFERENCENOOP, wdfqueryinterface/WdfDeviceInterfaceReferenceNoOp, WdfDeviceInterfaceReferenceNoOp, wdf.wdfdeviceinterfacereferencenoop, kmdf.wdfdeviceinterfacereferencenoop
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
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceInterfaceReferenceNoOp
product: Windows
targetos: Windows
req.typenames: "*PWDF_PDO_EVENT_CALLBACKS, WDF_PDO_EVENT_CALLBACKS"
req.product: Windows 10 or later.
---

# WdfDeviceInterfaceReferenceNoOp function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInterfaceReferenceNoOp</b> method can be used for driver-defined interfaces that do not require reference counts.


## -syntax


````
VOID WdfDeviceInterfaceReferenceNoOp(
  _In_ PVOID Context
);
````


## -parameters




### -param Context [in]

This parameter is not used.


## -returns


None



## -remarks


You can use the <b>WdfDeviceInterfaceReferenceNoOp</b> method's address as the <b>InterfaceReference</b> member of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure that is contained in the framework's <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure.

For more information about interface reference counts and the <b>WdfDeviceInterfaceReferenceNoOp</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-driver-defined-interfaces">Using Driver-Defined Interfaces</a>.



## -see-also

<a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceinterfacedereferencenoop.md">WdfDeviceInterfaceDereferenceNoOp</a>

<a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a>

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInterfaceReferenceNoOp method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

