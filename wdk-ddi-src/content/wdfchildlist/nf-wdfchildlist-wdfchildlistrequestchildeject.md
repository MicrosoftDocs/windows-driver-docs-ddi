---
UID: NF:wdfchildlist.WdfChildListRequestChildEject
title: WdfChildListRequestChildEject function
author: windows-driver-content
description: The WdfChildListRequestChildEject method informs the framework that a specified device is about to be ejected from its docking station.
old-location: wdf\wdfchildlistrequestchildeject.htm
old-project: wdf
ms.assetid: d7729edf-e92d-4707-83e2-fece90daeacf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFCHILDLISTREQUESTCHILDEJECT, wdfchildlist/WdfChildListRequestChildEject, WdfChildListRequestChildEject, wdf.wdfchildlistrequestchildeject, kmdf.wdfchildlistrequestchildeject, WdfChildListRequestChildEject method, DFDeviceObjectChildListRef_52991ad9-29ef-4ab8-b746-168fcc0b8e99.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfChildListRequestChildEject
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListRequestChildEject function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListRequestChildEject</b> method informs the framework that a specified device is about to be ejected from its docking station.


## -syntax


````
BOOLEAN WdfChildListRequestChildEject(
  _In_ WDFCHILDLIST                                 ChildList,
  _In_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
);
````


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param IdentificationDescription [in]

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -returns


<b>WdfChildListRequestChildEject</b> returns <b>TRUE</b> if the operation succeeds. If an input parameter is invalid, or if the framework cannot find the device in the child list, the method returns <b>FALSE</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks


A bus driver can call <b>WdfChildListRequestChildEject</b> or <a href="..\wdfpdo\nf-wdfpdo-wdfpdorequesteject.md">WdfPdoRequestEject</a> to report that the driver has detected an attempt to eject one of its enumerated child devices from the device's docking station. For example, the driver might detect that a user has pushed an eject button. 

If the driver is using dynamic bus enumeration and if the device's identification description is available, the driver can call <b>WdfChildListRequestChildEject</b>. If the framework device object for the device's PDO is available, the driver can call <a href="..\wdfpdo\nf-wdfpdo-wdfpdorequesteject.md">WdfPdoRequestEject</a>. 

The <b>WdfChildListRequestChildEject</b> method's <i>IdentificationDescription</i> parameter identifies the device that is being ejected. The device must be a member of the child list that the <i>ChildList</i> parameter represents.

The framework uses the identification description to locate the device in the child list.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.

For more information about ejectable devices, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.



## -see-also

<a href="..\wdfpdo\nf-wdfpdo-wdfpdorequesteject.md">WdfPdoRequestEject</a>

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListRequestChildEject method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

