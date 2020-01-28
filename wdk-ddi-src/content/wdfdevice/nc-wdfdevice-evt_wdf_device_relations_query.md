---
UID: NC:wdfdevice.EVT_WDF_DEVICE_RELATIONS_QUERY
title: EVT_WDF_DEVICE_RELATIONS_QUERY (wdfdevice.h)
description: A driver's EvtDeviceRelationsQuery event callback reports changes in the relationships among devices that are supported by the driver.
old-location: wdf\evtdevicerelationsquery.htm
tech.root: wdf
ms.assetid: 3a156696-1dd5-4383-a0cc-8d07ec92bdbf
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b34ffaf4-1e73-4463-87fd-31350656a7a5.xml, EVT_WDF_DEVICE_RELATIONS_QUERY, EVT_WDF_DEVICE_RELATIONS_QUERY callback, EvtDeviceRelationsQuery, EvtDeviceRelationsQuery callback function, kmdf.evtdevicerelationsquery, wdf.evtdevicerelationsquery, wdfdevice/EvtDeviceRelationsQuery
f1_keywords:
 - "wdfdevice/EvtDeviceRelationsQuery"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceRelationsQuery
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_RELATIONS_QUERY callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceRelationsQuery</i> event callback reports changes in the relationships among devices that are supported by the driver.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param RelationType [in]

A DEVICE_RELATION_TYPE-typed enumerator value. The DEVICE_RELATION_TYPE enumeration is defined in <i>wdm.h</i>.


## -remarks



To register the <i>EvtDeviceRelationsQuery</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>.

Most framework-based drivers do not need to provide this callback function.

During system initialization, the Plug and Play manager enumerates all of the devices on the system by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> request to the driver stack. If a framework-based driver has registered an <i>EvtDeviceRelationsQuery</i> callback function, the framework calls it. The function driver for the bus must report all of the child devices that are attached to the bus.

Additionally, after the framework calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinvalidatedevicerelations">IoInvalidateDeviceRelations</a> routine to report a changed relationship among the devices on the driver's bus, the Plug and Play manager sends another IRP_MN_QUERY_DEVICE_RELATIONS request to the driver stack. The framework then calls the driver's <i>EvtDeviceRelationsQuery</i> callback function so that the driver can provide details about the change. 

The type of work that a driver must do depends on the value received for the <i>RelationType</i> parameter. The value can be one of the following:



The framework can call the <i>EvtDeviceRelationsQuery</i> callback function with a <i>RelationType</i> value of <b>EjectionRelations</b> or <b>RemovalRelations</b> even if the device is being removed. 


#### Examples

To define an <i>EvtDeviceRelationsQuery</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceRelationsQuery</i> callback function that is named <i>MyDeviceRelationsQuery</i>, use the <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_RELATIONS_QUERY  MyDeviceRelationsQuery;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyDeviceRelationsQuery (
    WDFDEVICE  Device,
    DEVICE_RELATION_TYPE  RelationType
    )
 {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_RELATIONS_QUERY</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior?view=vs-2015">Annotating Function Behavior</a>.



