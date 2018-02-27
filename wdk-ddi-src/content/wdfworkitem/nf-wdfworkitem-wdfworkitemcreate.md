---
UID: NF:wdfworkitem.WdfWorkItemCreate
title: WdfWorkItemCreate function
author: windows-driver-content
description: The WdfWorkItemCreate method creates a framework work-item object, which can subsequently be added to the system's work-item queue.
old-location: wdf\wdfworkitemcreate.htm
old-project: wdf
ms.assetid: f5bb3af4-c687-47ad-88ce-d56067c78d6d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFWorkItemObjectRef_0041ea62-aa06-4e8b-8f84-807731ecc516.xml, WdfWorkItemCreate, WdfWorkItemCreate method, kmdf.wdfworkitemcreate, wdf.wdfworkitemcreate, wdfworkitem/WdfWorkItemCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfworkitem.h
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfWorkItemCreate
product: Windows
targetos: Windows
req.typenames: WDF_WMI_PROVIDER_CONFIG, *PWDF_WMI_PROVIDER_CONFIG
req.product: Windows 10 or later.
---

# WdfWorkItemCreate function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfWorkItemCreate</b> method creates a framework work-item object, which can subsequently be added to the system's work-item queue.


## -syntax


````
NTSTATUS WdfWorkItemCreate(
  _In_  PWDF_WORKITEM_CONFIG   Config,
  _In_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _Out_ WDFWORKITEM            *WorkItem
);
````


## -parameters




### -param Config [in]

A pointer to a caller-allocated <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure that the driver must have already initialized by calling <a href="..\wdfworkitem\nf-wdfworkitem-wdf_workitem_config_init.md">WDF_WORKITEM_CONFIG_INIT</a>.


### -param Attributes [in]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the work-item object. 


### -param WorkItem [out]

A pointer to a variable that receives a handle to the new work-item object.


## -returns



<b>WdfWorkItemCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The work-item object's parent is not a device object or the ancestor of a device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient system resources to create a work-item object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_INCOMPATIBLE_EXECUTION_LEVEL</b></dt>
</dl>
</td>
<td width="60%">
The <b>AutomaticSerialization</b> member in the <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure that the <i>Config</i> parameter points to is <b>TRUE</b>, but the parent object's execution level is not <b>WdfExecutionLevelPassive</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_PARENT_NOT_SPECIFIED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Attributes</i> parameter was <b>NULL</b>, or the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that <i>Attributes</i> specifies was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



After a driver calls <b>WdfWorkItemCreate</b> to create a work item, it typically stores item-specific information in the context memory of the work-item object. The driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function, which performs the work item's tasks, can access this information to determine the tasks that it must perform. (For more information about storing information in the context memory, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.)

After storing work-item information, the driver must call <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemenqueue.md">WdfWorkItemEnqueue</a> to add the work item to the system's work-item queue. When a system worker thread becomes available, the thread removes the work item from the queue and calls the <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function.

When the driver creates a work-item object, it must specify a parent object for the work-item object in the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. The parent object must be a framework device object or any object whose chain of parents leads to a framework device object. The framework will delete the work-item object when it deletes the device object.

To delete the work-item object earlier, the driver can call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>, as described in <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.

The driver can retrieve a work item's parent object by calling <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemgetparentobject.md">WdfWorkItemGetParentObject</a>. 

If your driver provides <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> or <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> callback functions for the work-item object, note that the framework calls these callback functions at IRQL = PASSIVE_LEVEL.

For more information about work items, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.


#### Examples

The following code example initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, initializes a <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure, and calls <b>WdfWorkItemCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status = STATUS_SUCCESS;
PWORKER_ITEM_CONTEXT  context;
WDF_OBJECT_ATTRIBUTES  attributes;
WDF_WORKITEM_CONFIG  workitemConfig;
WDFWORKITEM  hWorkItem;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE(
                                       &amp;attributes,
                                       WORKER_ITEM_CONTEXT
                                       );
attributes.ParentObject = FdoData-&gt;WdfDevice;

WDF_WORKITEM_CONFIG_INIT(
                         &amp;workitemConfig,
                         CallbackFunction
                         );

status = WdfWorkItemCreate(
                            &amp;workitemConfig,
                            &amp;attributes,
                            &amp;hWorkItem
                            );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemenqueue.md">WdfWorkItemEnqueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWorkItemCreate method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

