---
UID: NF:wdfchildlist.WdfChildListCreate
title: WdfChildListCreate function
author: windows-driver-content
description: The WdfChildListCreate method creates a child list for a specified parent device.
old-location: wdf\wdfchildlistcreate.htm
tech.root: wdf
ms.assetid: 88af6933-09f0-4248-9003-62f486d38645
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_750e00c2-f0a0-4a3f-a357-09de7568e268.xml, WdfChildListCreate, WdfChildListCreate method, kmdf.wdfchildlistcreate, wdf.wdfchildlistcreate, wdfchildlist/WdfChildListCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfChildListCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListCreate</b> method creates a child list for a specified parent device.


## -parameters




### -param Device [in]

A handle to a framework device object that represents the parent device.


### -param Config [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure that contains driver-supplied configuration information for the child list.


### -param ChildListAttributes [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the framework child-list object. (The structure's <b>ParentObject</b> member must be <b>NULL</b>.) 


### -param ChildList [out]

A pointer to a caller-allocated location that receives a handle to a framework child-list object.


## -returns



<b>WdfChildListCreate</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
An input parameter was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
An object could not be allocated.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



The framework creates a default child list for each framework device object that represents a functional device object (FDO). To use the default child list, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547235">WdfFdoGetDefaultChildList</a>. If your driver requires additional child lists, it can call <b>WdfChildListCreate</b> to create them.

The parent of each child-list object is the device's framework device object. The driver cannot change this parent, and the <b>ParentObject</b> member or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure must be <b>NULL</b>.

Your driver cannot delete the child-list object that <b>WdfChildListCreate</b> creates. The framework deletes the object at the proper time.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure and then calls <b>WdfChildListCreate</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_CHILD_LIST_CONFIG listConfig;

WDF_CHILD_LIST_CONFIG_INIT(
                           &amp;listConfig,
                           sizeof(PDO_IDENTIFICATION_DESCRIPTION),
                           My_EvtDeviceListCreatePdo
                           );

listConfig.AddressDescriptionSize = sizeof(PDO_ADDRESS_DESCRIPTION);

listConfig.EvtChildListScanForChildren = My_EvtChildListScanForChildren;

listConfig.EvtChildListIdentificationDescriptionDuplicate = My_EvtChildListIdentificationDescriptionDuplicate;
listConfig.EvtChildListIdentificationDescriptionCompare = My_EvtChildListIdentificationDescriptionCompare;
listConfig.EvtChildListIdentificationDescriptionCleanup = My_EvtChildListIdentificationDescriptionCleanup;

status = WdfChildListCreate(
                            device,
                            &amp;listConfig,
                            WDF_NO_OBJECT_ATTRIBUTES,
                            &amp;ParentDeviceContext-&gt;ChildList
                            );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551228">WDF_CHILD_LIST_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547235">WdfFdoGetDefaultChildList</a>
 

 

