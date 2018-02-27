---
UID: NF:wdfdpc.WdfDpcCreate
title: WdfDpcCreate function
author: windows-driver-content
description: The WdfDpcCreate method creates a framework DPC object and registers an EvtDpcFunc callback function.
old-location: wdf\wdfdpccreate.htm
old-project: wdf
ms.assetid: 46c6ffd1-4c01-4d1d-b7da-8f97f728ac71
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDpcObjectRef_865403a4-b5c1-4113-b3b1-1929285bb82d.xml, WdfDpcCreate, WdfDpcCreate method, kmdf.wdfdpccreate, wdf.wdfdpccreate, wdfdpc/WdfDpcCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDpcCreate
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDpcCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDpcCreate</b> method creates a framework DPC object and registers an <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function. 


## -syntax


````
NTSTATUS WdfDpcCreate(
  _In_  PWDF_DPC_CONFIG        Config,
  _In_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_ WDFDPC                 *Dpc
);
````


## -parameters




### -param Config [in]

A pointer to a caller-allocated <a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a> structure.


### -param Attributes [in]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the new DPC object. 


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
A parent object was not specified in the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure does not reference a framework device object or an object whose chain of parents leads to a framework device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member of the <a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a> structure is set to <b>TRUE</b>, but the parent object's <a href="..\wdfobject\ne-wdfobject-_wdf_execution_level.md">execution level</a> is set to <b>WdfExecutionLevelPassive</b>.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfDpcCreate</b> method might return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A driver typically calls <b>WdfDpcCreate</b> from within its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

When a driver creates a DPC object, it must specify a parent object in the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. The parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the DPC object when it deletes the device object.

Calling <b>WdfDpcCreate</b> creates a framework DPC object and registers an <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function. To schedule execution of the callback function, the driver must call <a href="..\wdfdpc\nf-wdfdpc-wdfdpcenqueue.md">WdfDpcEnqueue</a>. 

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the framework timer object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about using DPC objects, see <a href="https://msdn.microsoft.com/b6306d2c-a7be-4fc3-8123-4d2b5c60c988">Servicing an Interrupt</a>.


#### Examples

The following code example initializes a <a href="..\wdfdpc\nf-wdfdpc-wdf_dpc_config_init.md">WDF_DPC_CONFIG_INIT</a> structure and then creates a DPC object. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DPC_CONFIG dpcConfig;
WDF_OBJECT_ATTRIBUTES dpcAttributes;
NTSTATUS status;

WDF_DPC_CONFIG_INIT(
                    &amp;dpcConfig,
                    MyEvtDpcFunc
                    );
dpcConfig.AutomaticSerialization = TRUE;
WDF_OBJECT_ATTRIBUTES_INIT(&amp;dpcAttributes);
dpcAttributes.ParentObject = pDevExt-&gt;WdfDevice;
status = WdfDpcCreate(
                      &amp;dpcConfig,
                      &amp;dpcAttributes,
                      &amp;pDevExt-&gt;CompleteWriteDpc
                      );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfdpc\nf-wdfdpc-wdf_dpc_config_init.md">WDF_DPC_CONFIG_INIT</a>



<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a>



<a href="..\wdfdpc\nf-wdfdpc-wdfdpcenqueue.md">WdfDpcEnqueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDpcCreate method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

