---
UID: NF:wdfpdo.WdfPdoRetrieveIdentificationDescription
title: WdfPdoRetrieveIdentificationDescription function
author: windows-driver-content
description: The WdfPdoRetrieveIdentificationDescription method retrieves the identification description that is associated with a specified framework device object.
old-location: wdf\wdfpdoretrieveidentificationdescription.htm
old-project: wdf
ms.assetid: fac29ced-7acc-4c2a-ac8a-171b8dd1d45e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_fe883ca1-8b36-4ac1-b7ff-8c38bf098148.xml, WdfPdoRetrieveIdentificationDescription, WdfPdoRetrieveIdentificationDescription method, kmdf.wdfpdoretrieveidentificationdescription, wdf.wdfpdoretrieveidentificationdescription, wdfpdo/WdfPdoRetrieveIdentificationDescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
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
-	WdfPdoRetrieveIdentificationDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoRetrieveIdentificationDescription function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRetrieveIdentificationDescription</b> method retrieves the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> that is associated with a specified framework device object.


## -parameters




### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


### -param IdentificationDescription [in, out]

A pointer to a caller-allocated buffer that will receive the identification description. The identification description must contain a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:

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
The <i>Device</i> handle does not represent a PDO. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a device that was <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamically enumerated</a>, or if the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure does not contain the correct buffer size.

</td>
</tr>
</table>
 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551225">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548820">WdfPdoRetrieveAddressDescription</a>
 

 

