---
UID: NF:sti.IStillImageW.GetDeviceValue
title: IStillImageW::GetDeviceValue (sti.h)
description: The IStillImage::GetDeviceValue method returns registry information associated with a specified still image device.
old-location: image\istillimage_getdevicevalue.htm
tech.root: image
ms.assetid: 506c50fa-f162-4b30-bfb9-91987e064c39
ms.date: 05/03/2018
ms.keywords: GetDeviceValue, GetDeviceValue method [Imaging Devices], GetDeviceValue method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],GetDeviceValue method, IStillImageW.GetDeviceValue, IStillImageW::GetDeviceValue, image.istillimage_getdevicevalue, sti/IStillImageW::GetDeviceValue, stifnc_4b207dea-28ff-4f85-b8a7-43c038b3e810.xml
ms.topic: method
f1_keywords:
 - "sti/IStillImageW.GetDeviceValue"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- sti.h
api_name:
- IStillImageW.GetDeviceValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::GetDeviceValue


## -description


The <b>IStillImage::GetDeviceValue</b> method returns registry information associated with a specified still image device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.


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



The purpose of the <b>IStillImage::GetDeviceValue</b> method is to return the values currently assigned to device-specific <a href="https://docs.microsoft.com/windows-hardware/drivers/image/registry-entries-for-still-image-devices">Registry Entries for Still Image Devices</a>. The method calls <b>RegQueryValueEx</b> (described in the Microsoft Windows SDK documentation).

The <b>IStillImage::GetDeviceValue</b> method can return either an ANSI or a Unicode string. It can return a Unicode string only if your code is built as Unicode with Unicode defined.

Before calling <b>IStillImage::GetDeviceValue</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543801(v=vs.85)">IStillImage::SetDeviceValue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStillImageW</a>
 

 

