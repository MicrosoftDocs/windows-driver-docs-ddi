---
UID: NC:wdfdevice.EVT_WDF_DEVICE_RELATIONS_QUERY
title: EVT_WDF_DEVICE_RELATIONS_QUERY
author: windows-driver-content
description: A driver's EvtDeviceRelationsQuery event callback reports changes in the relationships among devices that are supported by the driver.
old-location: wdf\evtdevicerelationsquery.htm
old-project: wdf
ms.assetid: 3a156696-1dd5-4383-a0cc-8d07ec92bdbf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicerelationsquery, EvtDeviceRelationsQuery callback function, EvtDeviceRelationsQuery, EVT_WDF_DEVICE_RELATIONS_QUERY, EVT_WDF_DEVICE_RELATIONS_QUERY, wdfdevice/EvtDeviceRelationsQuery, DFDeviceObjectGeneralRef_b34ffaf4-1e73-4463-87fd-31350656a7a5.xml, kmdf.evtdevicerelationsquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Wdfdevice.h
apiname: 
-	EvtDeviceRelationsQuery
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_RELATIONS_QUERY callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceRelationsQuery</i> event callback reports changes in the relationships among devices that are supported by the driver.


## -prototype


````
EVT_WDF_DEVICE_RELATIONS_QUERY EvtDeviceRelationsQuery;

VOID EvtDeviceRelationsQuery(
  _In_ WDFDEVICE            Device,
  _In_ DEVICE_RELATION_TYPE RelationType
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param RelationType [in]

A DEVICE_RELATION_TYPE-typed enumerator value. The DEVICE_RELATION_TYPE enumeration is defined in <i>wdm.h</i>.


## -returns


None



## -remarks


To register the <i>EvtDeviceRelationsQuery</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>.

Most framework-based drivers do not need to provide this callback function.

During system initialization, the Plug and Play manager enumerates all of the devices on the system by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551670">IRP_MN_QUERY_DEVICE_RELATIONS</a> request to the driver stack. If a framework-based driver has registered an <i>EvtDeviceRelationsQuery</i> callback function, the framework calls it. The function driver for the bus must report all of the child devices that are attached to the bus.

Additionally, after the framework calls the <a href="..\wdm\nf-wdm-ioinvalidatedevicerelations.md">IoInvalidateDeviceRelations</a> routine to report a changed relationship among the devices on the driver's bus, the Plug and Play manager sends another IRP_MN_QUERY_DEVICE_RELATIONS request to the driver stack. The framework then calls the driver's <i>EvtDeviceRelationsQuery</i> callback function so that the driver can provide details about the change. 

The type of work that a driver must do depends on the value received for the <i>RelationType</i> parameter. The value can be one of the following:



The framework can call the <i>EvtDeviceRelationsQuery</i> callback function with a <i>RelationType</i> value of <b>EjectionRelations</b> or <b>RemovalRelations</b> even if the device is being removed. 


