---
UID: NF:sti.IStillImageW.CreateDevice
title: IStillImageW::CreateDevice method
author: windows-driver-content
description: The IStillImage::CreateDevice method creates an instance of the COM object that defines the IStiDevice COM Interface, and returns a pointer to the interface.
old-location: image\istillimage_createdevice.htm
old-project: image
ms.assetid: 24491434-1ad2-48fa-85e6-516efbe0550d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, CreateDevice method [Imaging Devices], CreateDevice method [Imaging Devices], IStillImage interface, CreateDevice,IStillImageW.CreateDevice, D, I, IStillImage interface [Imaging Devices], CreateDevice method, IStillImage::CreateDevice, IStillImageW, IStillImageW::CreateDevice, S, W, a, c, e, g, i, image.istillimage_createdevice, l, m, r, sti/IStillImage::CreateDevice, stifnc_07253e3c-b24e-4557-885f-3e17fb5dc293.xml, t, v"
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
req.lib: sti.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	sti.h
apiname:
-	IStillImage.CreateDevice
product: Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE
req.product: Windows 10 or later.
---

# IStillImageW::CreateDevice method


## -description


The <b>IStillImage::CreateDevice</b> method creates an instance of the COM object that defines the <a href="https://msdn.microsoft.com/b026fb74-9ce6-4d4e-8a5b-402731904064">IStiDevice COM Interface</a>, and returns a pointer to the interface.


## -syntax


````
HRESULT CreateDevice(
  [in]           LPWSTR     pwszDeviceName,
                 DWORD      dwMode,
  [out]          PSTIDEVICE *pDevice,
  [in, optional] LPUNKNOWN  punkOuter
);
````


## -parameters




### -param pwszDeviceName [in]

Caller-supplied pointer to a string representing an internal device name, obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543790">IStillImage::GetSTILaunchInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543784">IStillImage::GetDeviceList</a>.


### -param dwMode

Caller-supplied constant value indicating the <a href="https://msdn.microsoft.com/79af0d8f-dd04-4ff4-a047-f415562a16a5">Transfer Modes</a> in which the device is to be used. The following values are valid.

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

Receives a pointer to the <a href="https://msdn.microsoft.com/b026fb74-9ce6-4d4e-8a5b-402731904064">IStiDevice COM Interface</a>.


### -param punkOuter [in, optional]

Optional, caller-supplied pointer to the "controlling unknown" for object aggregation. See the following <b>Remarks</b> section.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



For an application to use the <b>IStiDevice</b> interface, it must first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543804">IStillImage::StiCreateInstance</a> to get a pointer to the <b>IStillImage</b> interface, then call <b>IStillImage::CreateDevice</b> to get a pointer to the <b>IStiDevice</b> interface. The pointer received in <i>pDevice</i> is used subsequently when calling <b>IStiDevice</b> methods, as illustrated in the sample still image code, to obtain access to the specified device.

If you want to create an aggregate COM object that includes <b>IStiDevice</b>, you must supply a pointer to the "controlling unknown" in <i>punkOuter</i>. In most cases you will not be creating an aggregate object, so <i>punkOuter</i> should be <b>NULL</b>. Object aggregation and the controlling unknown are described in the Microsoft Windows SDK documentation and in the <i>Component Object Model Specification</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543765">IStiDevice::Release</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStillImage::CreateDevice method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

