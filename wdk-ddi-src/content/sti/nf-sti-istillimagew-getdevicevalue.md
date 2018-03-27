---
UID: NF:sti.IStillImageW.GetDeviceValue
title: IStillImageW::GetDeviceValue method
author: windows-driver-content
description: The IStillImage::GetDeviceValue method returns registry information associated with a specified still image device.
old-location: image\istillimage_getdevicevalue.htm
old-project: image
ms.assetid: 506c50fa-f162-4b30-bfb9-91987e064c39
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetDeviceValue method [Imaging Devices], GetDeviceValue method [Imaging Devices], IStillImageW interface, GetDeviceValue,IStillImageW.GetDeviceValue, IStillImageW, IStillImageW interface [Imaging Devices], GetDeviceValue method, IStillImageW::GetDeviceValue, image.istillimage_getdevicevalue, sti/IStillImageW::GetDeviceValue, stifnc_4b207dea-28ff-4f85-b8a7-43c038b3e810.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sti.h
req.include-header: Sti.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	sti.h
api_name:
-	IStillImageW.GetDeviceValue
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::GetDeviceValue method


## -description


The <b>IStillImage::GetDeviceValue</b> method returns registry information associated with a specified still image device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.


### -param pValueName [in]

Caller-supplied pointer to a string representing a registry value name.


### -param pType [out]

Receives a constant representing the data type of the returned registry value.


### -param pData [out]

Caller-supplied pointer to a buffer to receive a returned value.


### -param cbData [in, out]

Caller-supplied size, in bytes, of the buffer pointed to by <i>pData</i>. The method modifies this value to represent the size of the returned data. If the specified buffer size is too small, the method supplies the required buffer size and returns an error code.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The purpose of the <b>IStillImage::GetDeviceValue</b> method is to return the values currently assigned to device-specific <a href="https://msdn.microsoft.com/cedc8afc-54c4-485e-989c-481fe30d899b">Registry Entries for Still Image Devices</a>. The method calls <b>RegQueryValueEx</b> (described in the Microsoft Windows SDK documentation).

The <b>IStillImage::GetDeviceValue</b> method can return either an ANSI or a Unicode string. It can return a Unicode string only if your code is built as Unicode with Unicode defined.

Before calling <b>IStillImage::GetDeviceValue</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543801">IStillImage::SetDeviceValue</a>



<a href="https://msdn.microsoft.com/a9ceee48-cbb5-4448-83b4-9c19fe89fcb9">IStillImageW</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImageW::GetDeviceValue method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

