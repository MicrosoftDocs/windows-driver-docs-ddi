---
UID: NF:wdfchildlist.WdfChildListRetrievePdo
title: WdfChildListRetrievePdo function
author: windows-driver-content
description: The WdfChildListRetrievePdo method returns a handle to the framework device object that is associated with a specified child description in a child list.
old-location: wdf\wdfchildlistretrievepdo.htm
old-project: wdf
ms.assetid: 8e6042e4-b004-4250-b208-b0614d2d11fd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfchildlist/WdfChildListRetrievePdo, wdf.wdfchildlistretrievepdo, WdfChildListRetrievePdo method, PFN_WDFCHILDLISTRETRIEVEPDO, kmdf.wdfchildlistretrievepdo, WdfChildListRetrievePdo, DFDeviceObjectChildListRef_d61bfe9b-d201-48ae-89f4-4e1566c0a396.xml
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
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfChildListRetrievePdo
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListRetrievePdo function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListRetrievePdo</b> method returns a handle to the framework device object that is associated with a specified child description in a child list.


## -syntax


````
WDFDEVICE WdfChildListRetrievePdo(
  _In_    WDFCHILDLIST             ChildList,
  _Inout_ PWDF_CHILD_RETRIEVE_INFO RetrieveInfo
);
````


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param RetrieveInfo [in, out]

A pointer to a driver-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure that the driver initializes with the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> of the child to be retrieved. 


## -returns


<b>WdfChildListRetrievePdo</b> returns a handle to the framework device object if the specified child device is located in the child list, if a framework device object exists for the child device, and if the framework has reported the device's existence to the PnP manager. Otherwise, the method returns <b>NULL</b>. The framework returns additional status information in the <b>Status</b> member of the <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks


Before calling <b>WdfChildListRetrievePdo</b>, the driver must place an identification description in a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure. 

The <b>WdfChildListRetrievePdo</b> method traverses the specified child list, looking for a child with an identification description that matches the one that the driver supplied in the WDF_CHILD_RETRIEVE_INFO structure. If the framework finds a match, and if the child has an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>, the framework fills in the structure's address description.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.



## -see-also

<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_retrieve_info_init.md">WDF_CHILD_RETRIEVE_INFO_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListRetrievePdo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

