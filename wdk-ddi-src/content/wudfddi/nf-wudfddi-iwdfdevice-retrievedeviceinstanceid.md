---
UID: NF:wudfddi.IWDFDevice.RetrieveDeviceInstanceId
title: IWDFDevice::RetrieveDeviceInstanceId
author: windows-driver-content
description: The RetrieveDeviceInstanceId method retrieves the identifier of an instance of a device.
old-location: wdf\iwdfdevice_retrievedeviceinstanceid.htm
tech.root: wdf
ms.assetid: 224277b4-447f-4981-aabf-90a10322c0df
ms.date: 2/26/2018
ms.keywords: IWDFDevice interface,RetrieveDeviceInstanceId method, IWDFDevice.RetrieveDeviceInstanceId, IWDFDevice::RetrieveDeviceInstanceId, RetrieveDeviceInstanceId, RetrieveDeviceInstanceId method, RetrieveDeviceInstanceId method,IWDFDevice interface, UMDFDeviceObjectRef_fef96c70-8877-4c1f-9e05-d4caf9a8ea28.xml, umdf.iwdfdevice_retrievedeviceinstanceid, wdf.iwdfdevice_retrievedeviceinstanceid, wudfddi/IWDFDevice::RetrieveDeviceInstanceId
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.RetrieveDeviceInstanceId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::RetrieveDeviceInstanceId


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveDeviceInstanceId</b> method retrieves the identifier of an instance of a device.


## -parameters




### -param Buffer [out, optional]

A pointer to a buffer that receives a <b>NULL</b>-terminated string that represents the identifier of an instance of the device, if the supplied buffer is non-<b>NULL</b> and <b>RetrieveDeviceInstanceId</b> is successful. 


### -param pdwSizeInChars [in, out]

A pointer to a variable that receives the number of characters, including the <b>NULL</b> character, in the string that <i>Buffer</i> points to.

If <i>Buffer</i> is <b>NULL</b>, the value that the driver supplied is zero. The framework then returns the size, in characters, that are required for the identifier string.

If <i>Buffer</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the identifier string. 


## -returns



<b>RetrieveDeviceInstanceId</b> returns S_OK for the following scenarios: 


<ul>
<li>The buffer that the <i>Buffer</i> parameter pointed to was non-<b>NULL</b> and large enough to hold the identifier string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by the <i>pdwSizeInChars</i> parameter to the number of characters in the string. 
</li>
<li>The buffer at <i>Buffer</i> was <b>NULL</b>, the driver preset the variable at <i>pdwSizeInChars</i> to 0, and the framework set the variable at <i>pdwSizeInChars</i> to the number of characters that are required for the string.</li>
</ul><b>RetrieveDeviceInstanceId</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer was non-<b>NULL</b> and did not contain enough space to hold the identifier string. The framework sets the variable at pdwSizeInChars to the number of characters that are required for the string.



<b>RetrieveDeviceInstanceId</b> might also return other HRESULT values.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>
 

 

