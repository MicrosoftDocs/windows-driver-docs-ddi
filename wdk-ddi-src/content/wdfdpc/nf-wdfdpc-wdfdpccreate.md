---
UID: NF:wdfdpc.WdfDpcCreate
title: WdfDpcCreate function (wdfdpc.h)
description: The WdfDpcCreate method creates a framework DPC object and registers an EvtDpcFunc callback function.
old-location: wdf\wdfdpccreate.htm
tech.root: wdf
ms.assetid: 46c6ffd1-4c01-4d1d-b7da-8f97f728ac71
ms.date: 02/26/2018
ms.keywords: DFDpcObjectRef_865403a4-b5c1-4113-b3b1-1929285bb82d.xml, WdfDpcCreate, WdfDpcCreate method, kmdf.wdfdpccreate, wdf.wdfdpccreate, wdfdpc/WdfDpcCreate
ms.topic: function
f1_keywords:
 - "wdfdpc/WdfDpcCreate"
req.header: wdfdpc.h
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDpcCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDpcCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDpcCreate</b> method creates a framework DPC object and registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function. 


## -parameters




### -param Config [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a> structure.


### -param Attributes [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the new DPC object. 


### -param Dpc [out]

A pointer to a location that receives a handle to the new framework DPC object.


## -returns



<b>WdfDpcCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A DPC object could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PARENT_NOT_SPECIFIED</b></dt>
</dl>
</td>
<td width="60%">
A parent object was not specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure does not reference a framework device object or an object whose chain of parents leads to a framework device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a> structure is set to <b>TRUE</b>, but the parent object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ne-wdfobject-_wdf_execution_level">execution level</a> is set to <b>WdfExecutionLevelPassive</b>.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfDpcCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



A driver typically calls <b>WdfDpcCreate</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

When a driver creates a DPC object, it must specify a parent object in the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. The parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the DPC object when it deletes the device object.

Calling <b>WdfDpcCreate</b> creates a framework DPC object and registers an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function. To schedule execution of the callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>. 

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the framework timer object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about using DPC objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/servicing-an-interrupt">Servicing an Interrupt</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nf-wdfdpc-wdf_dpc_config_init">WDF_DPC_CONFIG_INIT</a> structure and then creates a DPC object. 

```cpp
WDF_DPC_CONFIG dpcConfig;
WDF_OBJECT_ATTRIBUTES dpcAttributes;
NTSTATUS status;

WDF_DPC_CONFIG_INIT(
                    &dpcConfig,
                    MyEvtDpcFunc
                    );
dpcConfig.AutomaticSerialization = TRUE;
WDF_OBJECT_ATTRIBUTES_INIT(&dpcAttributes);
dpcAttributes.ParentObject = pDevExt->WdfDevice;
status = WdfDpcCreate(
                      &dpcConfig,
                      &dpcAttributes,
                      &pDevExt->CompleteWriteDpc
                      );
if (!NT_SUCCESS(status)) {
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/ns-wdfdpc-_wdf_dpc_config">WDF_DPC_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nf-wdfdpc-wdf_dpc_config_init">WDF_DPC_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>
 

 

