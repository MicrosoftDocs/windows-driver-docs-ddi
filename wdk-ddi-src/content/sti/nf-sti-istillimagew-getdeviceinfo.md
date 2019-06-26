---
UID: NF:sti.IStillImageW.GetDeviceInfo
title: IStillImageW::GetDeviceInfo (sti.h)
description: The IStillImage::GetDeviceInfo method returns hardware characteristics for a specified still image device.
old-location: image\istillimage_getdeviceinfo.htm
tech.root: image
ms.assetid: 4f3e1dcd-1885-4b9f-b033-19d91178d8ab
ms.date: 05/03/2018
ms.keywords: GetDeviceInfo, GetDeviceInfo method [Imaging Devices], GetDeviceInfo method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],GetDeviceInfo method, IStillImageW.GetDeviceInfo, IStillImageW::GetDeviceInfo, image.istillimage_getdeviceinfo, sti/IStillImageW::GetDeviceInfo, stifnc_a6d46551-9c0a-41f2-a5ed-ca5bc4d1b8c1.xml
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- sti.h
api_name:
- IStillImageW.GetDeviceInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::GetDeviceInfo


## -description


The <b>IStillImage::GetDeviceInfo</b> method returns hardware characteristics for a specified still image device.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.


### -param ppBuffer [out]

Receives a handle to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/ns-sti-_sti_device_informationw">STI_DEVICE_INFORMATION</a> structure.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStillImage::GetDeviceInfo</b> method returns an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sti/ns-sti-_sti_device_informationw">STI_DEVICE_INFORMATION</a> structure for the specified still-image device. Structure contents are typically used for creating user interface displays.

Before calling <b>IStillImage::GetDeviceInfo</b>, clients of the <b>IStillImage</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to obtain an <b>IStillImage</b> interface pointer.

When the caller has finished using the STI_DEVICE_INFORMATION structure referenced by <i>ppBuffer</i>, it must deallocate the buffer by calling <b>LocalFree</b> (described in the Microsoft Windows SDK documentation).




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">IStillImageW</a>
 

 

