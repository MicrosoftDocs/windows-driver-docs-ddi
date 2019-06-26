---
UID: NF:wdftimer.WdfTimerCreate
title: WdfTimerCreate function (wdftimer.h)
description: The WdfTimerCreate method creates a framework timer object.
old-location: wdf\wdftimercreate.htm
tech.root: wdf
ms.assetid: 577b7629-13ff-4a2d-9f9f-a140d8442bd3
ms.date: 02/26/2018
ms.keywords: DFTimerObjectRef_3388a92e-119d-4208-9cf5-2c934435ff25.xml, WdfTimerCreate, WdfTimerCreate method, kmdf.wdftimercreate, wdf.wdftimercreate, wdftimer/WdfTimerCreate
ms.topic: function
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfTimerCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfTimerCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfTimerCreate</b> method creates a framework timer object.


## -parameters




### -param Config [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/ns-wdftimer-_wdf_timer_config">WDF_TIMER_CONFIG</a> structure.


### -param Attributes [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains object attributes for the new timer object. 


### -param Timer [out]

A pointer to a location that receives a handle to the new framework timer object.


## -returns



<b>WdfTimerCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PARENT_NOT_SPECIFIED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Attributes</i> parameter was <b>NULL</b>, or the <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that <i>Attributes</i> specifies was <b>NULL</b>.

</td>
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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <b>ParentObject</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure did not reference a framework device object or an object whose chain of parents leads to a framework device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/ns-wdftimer-_wdf_timer_config">WDF_TIMER_CONFIG</a> structure was set to <b>TRUE</b>, but the parent device object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ne-wdfobject-_wdf_execution_level">execution level</a> was set to <b>WdfExecutionLevelPassive</b>.

</td>
</tr>
</table>
 

For a list of other return values that the <b>WdfTimerCreate</b> method might return, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-creation-errors">Framework Object Creation Errors</a>.

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



When your driver calls <b>WdfTimerCreate</b>, it must supply a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure and must specify a parent object in the structure's <b>ParentObject</b> member. The parent object can be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the timer object when it deletes the device object.

After creating a timer object, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a> to start the timer's clock regardless of whether the timer is periodic or not. 

If your driver provides <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_destroy">EvtDestroyCallback</a> callback functions for the framework timer object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/ns-wdftimer-_wdf_timer_config">WDF_TIMER_CONFIG</a> structure and a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure and then calls <b>WdfTimerCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_TIMER_CONFIG  timerConfig;
WDF_OBJECT_ATTRIBUTES  timerAttributes;
WDFTIMER  timerHandle;
NTSTATUS  status;

WDF_TIMER_CONFIG_INIT(
                      &timerConfig,
                      MyEvtTimerFunc
                      );

timerConfig.AutomaticSerialization = TRUE;

WDF_OBJECT_ATTRIBUTES_INIT(&timerAttributes);
timerAttributes.ParentObject = DeviceHandle;

status = WdfTimerCreate(
                        &timerConfig,
                        &timerAttributes,
                        &timerHandle
                        );

if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nf-wdfobject-wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/ns-wdftimer-_wdf_timer_config">WDF_TIMER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdf_timer_config_init">WDF_TIMER_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a>
 

 

