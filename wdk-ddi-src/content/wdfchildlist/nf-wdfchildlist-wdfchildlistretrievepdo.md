---
UID: NF:wdfchildlist.WdfChildListRetrievePdo
title: WdfChildListRetrievePdo function
author: windows-driver-content
description: The WdfChildListRetrievePdo method returns a handle to the framework device object that is associated with a specified child description in a child list.
old-location: wdf\wdfchildlistretrievepdo.htm
old-project: wdf
ms.assetid: 8e6042e4-b004-4250-b208-b0614d2d11fd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_d61bfe9b-d201-48ae-89f4-4e1566c0a396.xml, WdfChildListRetrievePdo, WdfChildListRetrievePdo method, kmdf.wdfchildlistretrievepdo, wdf.wdfchildlistretrievepdo, wdfchildlist/WdfChildListRetrievePdo
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfChildListRetrievePdo
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListRetrievePdo function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListRetrievePdo</b> method returns a handle to the framework device object that is associated with a specified child description in a child list.


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param RetrieveInfo [in, out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure that the driver initializes with the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> of the child to be retrieved. 


## -returns



<b>WdfChildListRetrievePdo</b> returns a handle to the framework device object if the specified child device is located in the child list, if a framework device object exists for the child device, and if the framework has reported the device's existence to the PnP manager. Otherwise, the method returns <b>NULL</b>. The framework returns additional status information in the <b>Status</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



Before calling <b>WdfChildListRetrievePdo</b>, the driver must place an identification description in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure. 

The <b>WdfChildListRetrievePdo</b> method traverses the specified child list, looking for a child with an identification description that matches the one that the driver supplied in the WDF_CHILD_RETRIEVE_INFO structure. If the framework finds a match, and if the child has an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>, the framework fills in the structure's address description.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example searches a child list to find a child device whose identification description contains a specified serial number, and it obtains a handle to the device object that represents the child device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDO_IDENTIFICATION_DESCRIPTION  description;
WDF_CHILD_RETRIEVE_INFO  info;
WDFDEVICE  hChild;

WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &amp;description.Header,
                                                 sizeof(description)
                                                 );

description.SerialNo = DeviceSerialNumber;

WDF_CHILD_RETRIEVE_INFO_INIT(
                             &amp;info,
                             &amp;description.Header
                             );

hChild = WdfChildListRetrievePdo(
                                 list,
                                 &amp;info
                                 );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551225">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551237">WDF_CHILD_RETRIEVE_INFO_INIT</a>
 

 

