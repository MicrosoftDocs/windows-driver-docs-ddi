---
UID: NF:sti.IStillImageW.CreateDevice
title: IStillImageW::CreateDevice (sti.h)
description: The IStillImage::CreateDevice method creates an instance of the COM object that defines the IStiDevice COM Interface, and returns a pointer to the interface.
old-location: image\istillimage_createdevice.htm
tech.root: image
ms.assetid: 24491434-1ad2-48fa-85e6-516efbe0550d
ms.date: 05/03/2018
ms.keywords: CreateDevice, CreateDevice method [Imaging Devices], CreateDevice method [Imaging Devices],IStillImageW interface, IStillImageW interface [Imaging Devices],CreateDevice method, IStillImageW.CreateDevice, IStillImageW::CreateDevice, image.istillimage_createdevice, sti/IStillImageW::CreateDevice, stifnc_07253e3c-b24e-4557-885f-3e17fb5dc293.xml
f1_keywords:
 - "sti/IStillImageW.CreateDevice"
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
- IStillImageW.CreateDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IStillImageW::CreateDevice


## -description


The <b>IStillImage::CreateDevice</b> method creates an instance of the COM object that defines the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevice-com-interface">IStiDevice COM Interface</a>, and returns a pointer to the interface.


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543790(v=vs.85)">IStillImage::GetSTILaunchInformation</a> or <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543784(v=vs.85)">IStillImage::GetDeviceList</a>.


### -param dwMode

Caller-supplied constant value indicating the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/transfer-modes">Transfer Modes</a> in which the device is to be used. The following values are valid.

<table>
<tr>
<th>Mode</th>
<th>Description</th>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_BOTH

</td>
<td>
The device is being opened for both obtaining status and transferring data.

</td>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_DATA

</td>
<td>
The device is being opened only for data transfers.

</td>
</tr>
<tr>
<td>
STI_DEVICE_CREATE_STATUS

</td>
<td>
The device is being opened only for obtaining status information.

</td>
</tr>
</table>
 


### -param pDevice [out]

Receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/istidevice-com-interface">IStiDevice COM Interface</a>.


### -param punkOuter [in, optional]

Optional, caller-supplied pointer to the "controlling unknown" for object aggregation. See the following <b>Remarks</b> section.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



For an application to use the <b>IStiDevice</b> interface, it must first call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543804(v=vs.85)">IStillImage::StiCreateInstance</a> to get a pointer to the <b>IStillImage</b> interface, then call <b>IStillImage::CreateDevice</b> to get a pointer to the <b>IStiDevice</b> interface. The pointer received in <i>pDevice</i> is used subsequently when calling <b>IStiDevice</b> methods, as illustrated in the sample still image code, to obtain access to the specified device.

If you want to create an aggregate COM object that includes <b>IStiDevice</b>, you must supply a pointer to the "controlling unknown" in <i>punkOuter</i>. In most cases you will not be creating an aggregate object, so <i>punkOuter</i> should be <b>NULL</b>. Object aggregation and the controlling unknown are described in the Microsoft Windows SDK documentation and in the <i>Component Object Model Specification</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-release">IStiDevice::Release</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStillImageW</a>
 

 

