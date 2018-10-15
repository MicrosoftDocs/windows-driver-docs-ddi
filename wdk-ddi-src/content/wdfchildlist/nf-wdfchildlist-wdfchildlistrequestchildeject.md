---
UID: NF:wdfchildlist.WdfChildListRequestChildEject
title: WdfChildListRequestChildEject function
author: windows-driver-content
description: The WdfChildListRequestChildEject method informs the framework that a specified device is about to be ejected from its docking station.
old-location: wdf\wdfchildlistrequestchildeject.htm
tech.root: wdf
ms.assetid: d7729edf-e92d-4707-83e2-fece90daeacf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_52991ad9-29ef-4ab8-b746-168fcc0b8e99.xml, WdfChildListRequestChildEject, WdfChildListRequestChildEject method, kmdf.wdfchildlistrequestchildeject, wdf.wdfchildlistrequestchildeject, wdfchildlist/WdfChildListRequestChildEject
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
-	WdfChildListRequestChildEject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListRequestChildEject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListRequestChildEject</b> method informs the framework that a specified device is about to be ejected from its docking station.


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param IdentificationDescription [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -returns



<b>WdfChildListRequestChildEject</b> returns <b>TRUE</b> if the operation succeeds. If an input parameter is invalid, or if the framework cannot find the device in the child list, the method returns <b>FALSE</b>.

A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



A bus driver can call <b>WdfChildListRequestChildEject</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548817">WdfPdoRequestEject</a> to report that the driver has detected an attempt to eject one of its enumerated child devices from the device's docking station. For example, the driver might detect that a user has pushed an eject button. 

If the driver is using dynamic bus enumeration and if the device's identification description is available, the driver can call <b>WdfChildListRequestChildEject</b>. If the framework device object for the device's PDO is available, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548817">WdfPdoRequestEject</a>. 

The <b>WdfChildListRequestChildEject</b> method's <i>IdentificationDescription</i> parameter identifies the device that is being ejected. The device must be a member of the child list that the <i>ChildList</i> parameter represents.

The framework uses the identification description to locate the device in the child list.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.

For more information about ejectable devices, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


#### Examples

For a code example that uses <b>WdfChildListRequestChildEject</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548817">WdfPdoRequestEject</a>
 

 

